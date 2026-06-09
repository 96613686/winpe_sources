# GameInputServerDevice::TryReadMouseInfo(GameInputMouseInfo *)

- ea: `0x180042310`
- end: `0x1800425ba`
- name: `?TryReadMouseInfo@GameInputServerDevice@@AEAAXPEAUGameInputMouseInfo@@@Z`
- size: `682`
- prototype: `void __fastcall(GameInputServerDevice *__hidden this, struct GameInputMouseInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180030308`

## callees

- `0x180001304`
- `0x180042310`
- `0x18004c8e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042389`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042511`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004246e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004246e`

## pseudocode

```c
void __fastcall GameInputServerDevice::TryReadMouseInfo(LPCWSTR *this, struct GameInputMouseInfo *a2)
{
  bool v2; // zf
  HANDLE FileW; // rax
  void *v5; // rbx
  DWORD v6; // eax
  int v7; // r9d
  int v8; // eax
  bool v9; // cc
  unsigned __int16 v10; // cx
  int v11; // eax
  DWORD LastError; // eax
  int v13; // r9d
  DWORD BytesReturned; // [rsp+40h] [rbp-40h] BYREF
  int InBuffer; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD v16; // [rsp+48h] [rbp-38h] BYREF
  const char *v17; // [rsp+50h] [rbp-30h] BYREF
  const char *v18; // [rsp+58h] [rbp-28h] BYREF
  __int64 OutBuffer; // [rsp+60h] [rbp-20h] BYREF
  int v20; // [rsp+68h] [rbp-18h]

  v2 = byte_180069913 == 0;
  *(_QWORD *)a2 = 7;
  *((_DWORD *)a2 + 2) = 0;
  *((_WORD *)a2 + 6) = 256;
  if ( !v2 )
    return;
  FileW = CreateFileW(this[24], 0x20000000u, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    LOWORD(InBuffer) = 0;
    BytesReturned = 0;
    OutBuffer = 0;
    v20 = 0;
    if ( !DeviceIoControl(FileW, 0xF0000u, &InBuffer, 2u, &OutBuffer, 0xCu, &BytesReturned, 0) || BytesReturned != 12 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v16 = LastError;
        LODWORD(v17) = 344;
        v18 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018 & 0x400,
          (unsigned int)&byte_180062497,
          qword_180069018,
          v13,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16);
      }
      goto LABEL_32;
    }
    v8 = WORD2(OutBuffer);
    v9 = WORD2(OutBuffer) <= 0x2710u;
    *(_DWORD *)a2 = 3;
    if ( !v9 )
      v8 = 10000;
    v10 = WORD1(OutBuffer);
    *((_DWORD *)a2 + 1) = v8;
    v11 = 3;
    if ( v10 > 2u )
    {
      *(_DWORD *)a2 = 7;
      v11 = 7;
    }
    if ( v10 > 3u )
    {
      v11 |= 8u;
      *(_DWORD *)a2 = v11;
    }
    if ( v10 > 4u )
      *(_DWORD *)a2 = v11 | 0x10;
    if ( (unsigned __int16)OutBuffer != 1
      && (unsigned __int16)OutBuffer != 2
      && (unsigned __int16)OutBuffer != 4
      && (unsigned __int16)OutBuffer != 8
      && (unsigned __int16)OutBuffer != 16 )
    {
      if ( (unsigned __int16)OutBuffer == 32 || (unsigned __int16)OutBuffer == 64 )
        goto LABEL_26;
      if ( (unsigned __int16)OutBuffer != 128 )
      {
        if ( (unsigned __int16)OutBuffer != 256 )
        {
LABEL_32:
          CloseHandle(v5);
          return;
        }
LABEL_26:
        *((_BYTE *)a2 + 13) = 1;
        goto LABEL_32;
      }
    }
    *((_BYTE *)a2 + 13) = 0;
    goto LABEL_32;
  }
  v6 = GetLastError();
  if ( (unsigned int)dword_180069000 > 2
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    BytesReturned = v6;
    InBuffer = 273;
    v17 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018 & 0x400,
      (unsigned int)&unk_1800612C0,
      qword_180069018,
      v7,
      (__int64)&v17,
      (__int64)&InBuffer,
      (__int64)&BytesReturned);
  }
}

```

## disassembly

```asm
0x180042310  mov     r11, rsp
0x180042313  mov     [r11+18h], rbx
0x180042317  mov     [r11+20h], rsi
0x18004231b  push    rbp
0x18004231c  push    rdi
0x18004231d  push    r12
0x18004231f  mov     rbp, rsp
0x180042322  sub     rsp, 80h
0x180042329  mov     rax, cs:__security_cookie
0x180042330  xor     rax, rsp
0x180042333  mov     [rbp+var_10], rax
0x180042337  cmp     cs:byte_180069913, 0
0x18004233e  mov     rdi, rdx
0x180042341  mov     qword ptr [rdx], 7
0x180042348  mov     dword ptr [rdx+8], 0
0x18004234f  mov     word ptr [rdx+0Ch], 100h
0x180042355  jnz     loc_180042595
0x18004235b  mov     rcx, [rcx+0C0h]; lpFileName
0x180042362  mov     r12d, 3
0x180042368  mov     qword ptr [r11-68h], 0
0x180042370  xor     r9d, r9d; lpSecurityAttributes
0x180042373  mov     [rsp+80h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004237b  mov     edx, 20000000h; dwDesiredAccess
0x180042380  mov     [r11-78h], r12d
0x180042384  lea     r8d, [r12-2]; dwShareMode
0x180042389  call    cs:__imp_CreateFileW
0x180042390  nop     dword ptr [rax+rax+00h]
0x180042395  mov     rbx, rax
0x180042398  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004239c  jnz     loc_18004242B
0x1800423a2  call    cs:__imp_GetLastError
0x1800423a9  nop     dword ptr [rax+rax+00h]
0x1800423ae  mov     ecx, cs:dword_180069000
0x1800423b4  lea     esi, [rbx+3]
0x1800423b7  cmp     ecx, esi
0x1800423b9  jbe     loc_180042595
0x1800423bf  mov     r8, cs:qword_180069018
0x1800423c6  mov     edx, 400h
0x1800423cb  mov     rcx, cs:qword_180069010
0x1800423d2  test    rdx, rcx
0x1800423d5  jz      loc_180042595
0x1800423db  mov     rcx, r8
0x1800423de  and     rcx, rdx
0x1800423e1  cmp     rcx, r8
0x1800423e4  jnz     loc_180042595
0x1800423ea  mov     [rbp+BytesReturned], eax
0x1800423ed  lea     rdx, unk_1800612C0
0x1800423f4  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x1800423fb  mov     [rbp+InBuffer], 111h
0x180042402  mov     [rbp+var_30], rax
0x180042406  lea     rax, [rbp+BytesReturned]
0x18004240a  mov     [rsp+80h+lpBytesReturned], rax
0x18004240f  lea     rax, [rbp+InBuffer]
0x180042413  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x180042418  lea     rax, [rbp+var_30]
0x18004241c  mov     [rsp+80h+lpOutBuffer], rax
0x180042421  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180042426  jmp     loc_180042595
0x18004242b  xor     eax, eax
0x18004242d  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180042431  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x180042436  mov     esi, 2
0x18004243b  mov     word ptr [rbp+InBuffer], ax
0x18004243f  mov     r9d, esi; nInBufferSize
0x180042442  mov     [rbp+BytesReturned], eax
0x180042445  mov     edx, 0F0000h; dwIoControlCode
0x18004244a  mov     [rbp+OutBuffer], rax
0x18004244e  mov     rcx, rbx; hDevice
0x180042451  mov     [rbp+var_18], eax
0x180042454  lea     rax, [rbp+BytesReturned]
0x180042458  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18004245d  lea     rax, [rbp+OutBuffer]
0x180042461  mov     [rsp+80h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x180042469  mov     [rsp+80h+lpOutBuffer], rax; lpOutBuffer
0x18004246e  call    cs:__imp_DeviceIoControl
0x180042475  nop     dword ptr [rax+rax+00h]
0x18004247a  test    eax, eax
0x18004247c  jz      loc_180042511
0x180042482  cmp     [rbp+BytesReturned], 0Ch
0x180042486  jnz     loc_180042511
0x18004248c  movzx   eax, word ptr [rbp+OutBuffer+4]
0x180042490  mov     ecx, 2710h
0x180042495  cmp     eax, ecx
0x180042497  mov     [rdi], r12d
0x18004249a  cmova   eax, ecx
0x18004249d  movzx   ecx, word ptr [rbp+OutBuffer+2]
0x1800424a1  mov     [rdi+4], eax
0x1800424a4  mov     eax, r12d
0x1800424a7  cmp     cx, si
0x1800424aa  jbe     short loc_1800424B5
0x1800424ac  mov     dword ptr [rdi], 7
0x1800424b2  lea     eax, [rsi+5]
0x1800424b5  cmp     cx, r12w
0x1800424b9  jbe     short loc_1800424C0
0x1800424bb  or      eax, 8
0x1800424be  mov     [rdi], eax
0x1800424c0  mov     edx, 4
0x1800424c5  cmp     cx, dx
0x1800424c8  jbe     short loc_1800424CF
0x1800424ca  or      eax, 10h
0x1800424cd  mov     [rdi], eax
0x1800424cf  movzx   ecx, word ptr [rbp+OutBuffer]
0x1800424d3  sub     ecx, 1
0x1800424d6  jz      short loc_18004250B
0x1800424d8  sub     ecx, 1
0x1800424db  jz      short loc_18004250B
0x1800424dd  sub     ecx, esi
0x1800424df  jz      short loc_18004250B
0x1800424e1  sub     ecx, edx
0x1800424e3  jz      short loc_18004250B
0x1800424e5  sub     ecx, 8
0x1800424e8  jz      short loc_18004250B
0x1800424ea  sub     ecx, 10h
0x1800424ed  jz      short loc_180042505
0x1800424ef  sub     ecx, 20h ; ' '
0x1800424f2  jz      short loc_180042505
0x1800424f4  sub     ecx, 40h ; '@'
0x1800424f7  jz      short loc_18004250B
0x1800424f9  cmp     ecx, 80h
0x1800424ff  jnz     loc_180042586
0x180042505  mov     byte ptr [rdi+0Dh], 1
0x180042509  jmp     short loc_180042586
0x18004250b  mov     byte ptr [rdi+0Dh], 0
0x18004250f  jmp     short loc_180042586
0x180042511  call    cs:__imp_GetLastError
0x180042518  nop     dword ptr [rax+rax+00h]
0x18004251d  mov     ecx, cs:dword_180069000
0x180042523  cmp     ecx, esi
0x180042525  jbe     short loc_180042586
0x180042527  mov     r8, cs:qword_180069018
0x18004252e  mov     edx, 400h
0x180042533  mov     rcx, cs:qword_180069010
0x18004253a  test    rdx, rcx
0x18004253d  jz      short loc_180042586
0x18004253f  mov     rcx, r8
0x180042542  and     rcx, rdx
0x180042545  cmp     rcx, r8
0x180042548  jnz     short loc_180042586
0x18004254a  mov     [rbp+var_38], eax
0x18004254d  lea     rdx, byte_180062497
0x180042554  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x18004255b  mov     dword ptr [rbp+var_30], 158h
0x180042562  mov     [rbp+var_28], rax
0x180042566  lea     rax, [rbp+var_38]
0x18004256a  mov     [rsp+80h+lpBytesReturned], rax
0x18004256f  lea     rax, [rbp+var_30]
0x180042573  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x180042578  lea     rax, [rbp+var_28]
0x18004257c  mov     [rsp+80h+lpOutBuffer], rax
0x180042581  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180042586  mov     rcx, rbx; hObject
0x180042589  call    cs:__imp_CloseHandle
0x180042590  nop     dword ptr [rax+rax+00h]
0x180042595  mov     rcx, [rbp+var_10]
0x180042599  xor     rcx, rsp; StackCookie
0x18004259c  call    __security_check_cookie
0x1800425a1  lea     r11, [rsp+80h+var_s0]
0x1800425a9  mov     rbx, [r11+30h]
0x1800425ad  mov     rsi, [r11+38h]
0x1800425b1  mov     rsp, r11
0x1800425b4  pop     r12
0x1800425b6  pop     rdi
0x1800425b7  pop     rbp
0x1800425b8  retn
```

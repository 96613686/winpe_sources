# GameInputServerDevice::TryReadKeyboardInfo(GameInputKeyboardInfo *)

- ea: `0x180041ff0`
- end: `0x180042308`
- name: `?TryReadKeyboardInfo@GameInputServerDevice@@AEAAXPEAUGameInputKeyboardInfo@@@Z`
- size: `792`
- prototype: `void __fastcall(GameInputServerDevice *__hidden this, struct GameInputKeyboardInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180030308`

## callees

- `0x180001304`
- `0x1800244ac`
- `0x180041ff0`
- `0x18004c8e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042088`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042088`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800422d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800422d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800421c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004226a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800421c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004226a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004216d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004216d`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardType` at `0x18004222f`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardType` at `0x18004222f`

## pseudocode

```c
void __fastcall GameInputServerDevice::TryReadKeyboardInfo(
        GameInputServerDevice *this,
        struct GameInputKeyboardInfo *a2)
{
  HANDLE FileW; // rax
  void *v5; // rbx
  DWORD LastError; // eax
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ecx
  unsigned int v10; // eax
  int v11; // ecx
  unsigned __int16 v12; // ax
  DWORD v13; // eax
  int v14; // r8d
  int v15; // r9d
  int KeyboardType; // eax
  int v17; // eax
  int v18; // eax
  DWORD v19; // eax
  int v20; // r8d
  int v21; // r9d
  DWORD BytesReturned; // [rsp+40h] [rbp-9h] BYREF
  int InBuffer; // [rsp+44h] [rbp-5h] BYREF
  int v24; // [rsp+48h] [rbp-1h] BYREF
  const char *v25; // [rsp+50h] [rbp+7h] BYREF
  const char *v26; // [rsp+58h] [rbp+Fh] BYREF
  _WORD OutBuffer[16]; // [rsp+60h] [rbp+17h] BYREF

  *(_DWORD *)a2 = -1;
  *((_DWORD *)a2 + 1) = KeyboardLookupTable::KlidFromHkl(*(HKL *)(*((_QWORD *)this + 8) + 224LL));
  *((_DWORD *)a2 + 2) = 104;
  *((_DWORD *)a2 + 3) = 12;
  *((_DWORD *)a2 + 4) = 16;
  *(_QWORD *)((char *)a2 + 20) = 4;
  *((_QWORD *)a2 + 4) = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 24), 0x20000000u, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      BytesReturned = LastError;
      InBuffer = 168;
      v25 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018 & 0x400,
        (unsigned int)byte_1800619BD,
        v7,
        v8,
        (__int64)&v25,
        (__int64)&InBuffer,
        (__int64)&BytesReturned);
    }
  }
  else
  {
    LOWORD(InBuffer) = 0;
    BytesReturned = 0;
    memset(OutBuffer, 0, 28);
    if ( DeviceIoControl(FileW, 0xB0000u, &InBuffer, 2u, OutBuffer, 0x1Cu, &BytesReturned, 0) && BytesReturned == 28 )
    {
      v9 = OutBuffer[4];
      *((_DWORD *)a2 + 3) = OutBuffer[2];
      *((_DWORD *)a2 + 2) = v9;
      v10 = *((_DWORD *)a2 + 4);
      if ( v10 >= v9 )
        v10 = v9;
      v11 = LOBYTE(OutBuffer[0]);
      *((_DWORD *)a2 + 4) = v10;
      v12 = HIBYTE(OutBuffer[0]);
      *((_DWORD *)a2 + 6) = HIBYTE(OutBuffer[0]);
      *((_DWORD *)a2 + 5) = v11;
      if ( v11 == 7 )
        *((_DWORD *)a2 + 6) = v12;
    }
    else
    {
      v13 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v24 = v13;
        LODWORD(v25) = 207;
        v26 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018 & 0x400,
          (unsigned int)byte_1800602A1,
          v14,
          v15,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24);
      }
    }
    KeyboardType = GetKeyboardType(0);
    if ( KeyboardType )
    {
      v17 = KeyboardType - 4;
      if ( v17 )
      {
        v18 = v17 - 3;
        if ( v18 )
        {
          if ( v18 == 1 )
            *(_DWORD *)a2 = 2;
        }
        else
        {
          *(_DWORD *)a2 = 4;
        }
      }
      else
      {
        *(_DWORD *)a2 = 0;
      }
    }
    else
    {
      v19 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        LODWORD(v25) = v19;
        v24 = 221;
        v26 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018 & 0x400,
          (unsigned int)word_180061A3A,
          v20,
          v21,
          (__int64)&v26,
          (__int64)&v24,
          (__int64)&v25);
      }
    }
    CloseHandle(v5);
  }
}

```

## disassembly

```asm
0x180041ff0  mov     [rsp-8+arg_10], rbx
0x180041ff5  mov     [rsp-8+arg_18], rsi
0x180041ffa  push    rbp
0x180041ffb  push    rdi
0x180041ffc  push    r14
0x180041ffe  lea     rbp, [rsp-47h]
0x180042003  sub     rsp, 90h
0x18004200a  mov     rax, cs:__security_cookie
0x180042011  xor     rax, rsp
0x180042014  mov     [rbp+57h+var_20], rax
0x180042018  mov     rbx, rcx
0x18004201b  mov     dword ptr [rdx], 0FFFFFFFFh
0x180042021  mov     rcx, [rcx+40h]
0x180042025  mov     rdi, rdx
0x180042028  mov     rcx, [rcx+0E0h]; HKL
0x18004202f  call    ?KlidFromHkl@KeyboardLookupTable@@SAIPEAUHKL__@@@Z; KeyboardLookupTable::KlidFromHkl(HKL__ *)
0x180042034  xor     r9d, r9d; lpSecurityAttributes
0x180042037  mov     [rdi+4], eax
0x18004203a  mov     dword ptr [rdi+8], 68h ; 'h'
0x180042041  mov     edx, 20000000h; dwDesiredAccess
0x180042046  mov     dword ptr [rdi+0Ch], 0Ch
0x18004204d  mov     dword ptr [rdi+10h], 10h
0x180042054  mov     qword ptr [rdi+14h], 4
0x18004205c  lea     r8d, [r9+1]; dwShareMode
0x180042060  mov     qword ptr [rdi+20h], 0
0x180042068  mov     rcx, [rbx+0C0h]; lpFileName
0x18004206f  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180042078  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180042080  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180042088  call    cs:__imp_CreateFileW
0x18004208f  nop     dword ptr [rax+rax+00h]
0x180042094  mov     rbx, rax
0x180042097  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004209b  jnz     loc_180042128
0x1800420a1  call    cs:__imp_GetLastError
0x1800420a8  nop     dword ptr [rax+rax+00h]
0x1800420ad  mov     ecx, cs:dword_180069000
0x1800420b3  cmp     ecx, 2
0x1800420b6  jbe     loc_1800422E3
0x1800420bc  mov     rdx, cs:qword_180069018
0x1800420c3  mov     esi, 400h
0x1800420c8  mov     rcx, cs:qword_180069010
0x1800420cf  test    rsi, rcx
0x1800420d2  jz      loc_1800422E3
0x1800420d8  mov     rcx, rdx
0x1800420db  and     rcx, rsi
0x1800420de  cmp     rcx, rdx
0x1800420e1  jnz     loc_1800422E3
0x1800420e7  mov     [rbp+57h+BytesReturned], eax
0x1800420ea  lea     r14, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x1800420f1  lea     rax, [rbp+57h+BytesReturned]
0x1800420f5  mov     [rbp+57h+InBuffer], 0A8h
0x1800420fc  mov     [rsp+0A0h+hTemplateFile], rax
0x180042101  lea     rdx, byte_1800619BD
0x180042108  lea     rax, [rbp+57h+InBuffer]
0x18004210c  mov     [rbp+57h+var_50], r14
0x180042110  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x180042115  lea     rax, [rbp+57h+var_50]
0x180042119  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x18004211e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180042123  jmp     loc_1800422E3
0x180042128  xor     eax, eax
0x18004212a  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18004212e  mov     [rsp+0A0h+lpOverlapped], rax; lpOverlapped
0x180042133  xorps   xmm0, xmm0
0x180042136  mov     word ptr [rbp+57h+InBuffer], ax
0x18004213a  mov     r9d, 2; nInBufferSize
0x180042140  mov     [rbp+57h+BytesReturned], eax
0x180042143  mov     edx, 0B0000h; dwIoControlCode
0x180042148  lea     rax, [rbp+57h+BytesReturned]
0x18004214c  mov     rcx, rbx; hDevice
0x18004214f  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x180042154  lea     rax, [rbp+57h+OutBuffer]
0x180042158  movups  xmmword ptr [rbp+57h+OutBuffer], xmm0
0x18004215c  mov     [rsp+0A0h+dwFlagsAndAttributes], 1Ch; nOutBufferSize
0x180042164  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; lpOutBuffer
0x180042169  movups  xmmword ptr [rbp+57h+OutBuffer+0Ch], xmm0
0x18004216d  call    cs:__imp_DeviceIoControl
0x180042174  nop     dword ptr [rax+rax+00h]
0x180042179  mov     esi, 400h
0x18004217e  lea     r14, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180042185  test    eax, eax
0x180042187  jz      short loc_1800421C3
0x180042189  cmp     [rbp+57h+BytesReturned], 1Ch
0x18004218d  jnz     short loc_1800421C3
0x18004218f  movzx   ecx, word ptr [rbp+57h+OutBuffer+8]
0x180042193  movzx   eax, word ptr [rbp+57h+OutBuffer+4]
0x180042197  mov     [rdi+0Ch], eax
0x18004219a  mov     [rdi+8], ecx
0x18004219d  mov     eax, [rdi+10h]
0x1800421a0  cmp     eax, ecx
0x1800421a2  cmovnb  eax, ecx
0x1800421a5  movzx   ecx, [rbp+57h+OutBuffer]
0x1800421a9  mov     [rdi+10h], eax
0x1800421ac  movzx   eax, [rbp+57h+OutBuffer+1]
0x1800421b0  mov     [rdi+18h], eax
0x1800421b3  mov     [rdi+14h], ecx
0x1800421b6  cmp     ecx, 7
0x1800421b9  jnz     short loc_18004222D
0x1800421bb  movzx   eax, ax
0x1800421be  mov     [rdi+18h], eax
0x1800421c1  jmp     short loc_18004222D
0x1800421c3  call    cs:__imp_GetLastError
0x1800421ca  nop     dword ptr [rax+rax+00h]
0x1800421cf  mov     ecx, cs:dword_180069000
0x1800421d5  cmp     ecx, 2
0x1800421d8  jbe     short loc_18004222D
0x1800421da  mov     rdx, cs:qword_180069018
0x1800421e1  mov     rcx, cs:qword_180069010
0x1800421e8  test    rsi, rcx
0x1800421eb  jz      short loc_18004222D
0x1800421ed  mov     rcx, rdx
0x1800421f0  and     rcx, rsi
0x1800421f3  cmp     rcx, rdx
0x1800421f6  jnz     short loc_18004222D
0x1800421f8  mov     [rbp+57h+var_58], eax
0x1800421fb  lea     rdx, byte_1800602A1
0x180042202  lea     rax, [rbp+57h+var_58]
0x180042206  mov     dword ptr [rbp+57h+var_50], 0CFh
0x18004220d  mov     [rsp+0A0h+hTemplateFile], rax
0x180042212  lea     rax, [rbp+57h+var_50]
0x180042216  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x18004221b  lea     rax, [rbp+57h+var_48]
0x18004221f  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x180042224  mov     [rbp+57h+var_48], r14
0x180042228  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004222d  xor     ecx, ecx; nTypeFlag
0x18004222f  call    cs:__imp_GetKeyboardType
0x180042236  nop     dword ptr [rax+rax+00h]
0x18004223b  test    eax, eax
0x18004223d  jz      short loc_18004226A
0x18004223f  sub     eax, 4
0x180042242  jz      short loc_180042262
0x180042244  sub     eax, 3
0x180042247  jz      short loc_18004225A
0x180042249  cmp     eax, 1
0x18004224c  jnz     loc_1800422D4
0x180042252  mov     dword ptr [rdi], 2
0x180042258  jmp     short loc_1800422D4
0x18004225a  mov     dword ptr [rdi], 4
0x180042260  jmp     short loc_1800422D4
0x180042262  mov     dword ptr [rdi], 0
0x180042268  jmp     short loc_1800422D4
0x18004226a  call    cs:__imp_GetLastError
0x180042271  nop     dword ptr [rax+rax+00h]
0x180042276  mov     ecx, cs:dword_180069000
0x18004227c  cmp     ecx, 2
0x18004227f  jbe     short loc_1800422D4
0x180042281  mov     rdx, cs:qword_180069018
0x180042288  mov     rcx, cs:qword_180069010
0x18004228f  test    rsi, rcx
0x180042292  jz      short loc_1800422D4
0x180042294  mov     rcx, rdx
0x180042297  and     rcx, rsi
0x18004229a  cmp     rcx, rdx
0x18004229d  jnz     short loc_1800422D4
0x18004229f  mov     dword ptr [rbp+57h+var_50], eax
0x1800422a2  lea     rdx, word_180061A3A
0x1800422a9  lea     rax, [rbp+57h+var_50]
0x1800422ad  mov     [rbp+57h+var_58], 0DDh
0x1800422b4  mov     [rsp+0A0h+hTemplateFile], rax
0x1800422b9  lea     rax, [rbp+57h+var_58]
0x1800422bd  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], rax
0x1800422c2  lea     rax, [rbp+57h+var_48]
0x1800422c6  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax
0x1800422cb  mov     [rbp+57h+var_48], r14
0x1800422cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800422d4  mov     rcx, rbx; hObject
0x1800422d7  call    cs:__imp_CloseHandle
0x1800422de  nop     dword ptr [rax+rax+00h]
0x1800422e3  mov     rcx, [rbp+57h+var_20]
0x1800422e7  xor     rcx, rsp; StackCookie
0x1800422ea  call    __security_check_cookie
0x1800422ef  lea     r11, [rsp+0A0h+var_10]
0x1800422f7  mov     rbx, [r11+30h]
0x1800422fb  mov     rsi, [r11+38h]
0x1800422ff  mov     rsp, r11
0x180042302  pop     r14
0x180042304  pop     rdi
0x180042305  pop     rbp
0x180042306  retn
```

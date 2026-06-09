# RdVhd::Util::CVhdHelper::GetDiskNumberForVolume(ushort const *,ulong *)

- ea: `0x1800498cc`
- end: `0x180049b39`
- name: `?GetDiskNumberForVolume@CVhdHelper@Util@RdVhd@@QEBAJPEBGPEAK@Z`
- size: `621`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdHelper *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180052940`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18001a880`
- `0x18001a8d0`
- `0x18003114c`
- `0x180037110`
- `0x1800488e4`
- `0x180048b28`
- `0x1800498cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049b0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049a67`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049a67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180049af2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180049af2`

## string_xrefs

- `0x180049949`: `szVolumeGuidPath`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::GetDiskNumberForVolume(
        RdVhd::Util::CVhdHelper *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v4; // rcx
  __int64 v5; // rdx
  const wchar_t *v6; // r9
  int v7; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  _DWORD *v13; // r14
  void **v15; // [rsp+40h] [rbp-30h] BYREF
  int v16; // [rsp+48h] [rbp-28h]
  __int64 v17; // [rsp+4Ch] [rbp-24h]
  int v18; // [rsp+54h] [rbp-1Ch]
  __int64 v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+60h] [rbp-10h]
  DWORD BytesReturned; // [rsp+90h] [rbp+20h] BYREF
  int v22; // [rsp+94h] [rbp+24h]

  v22 = HIDWORD(this);
  v17 = 128;
  v15 = &CPathString::`vftable';
  v19 = 0;
  v18 = 0;
  v20 = 0x8000000;
  v16 = 0;
  BytesReturned = 0;
  if ( !a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 108;
    v6 = L"szVolumeGuidPath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v4 + 2), v5, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v6);
LABEL_7:
    v7 = -2147024809;
    goto LABEL_37;
  }
  if ( !a3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 109;
    v6 = L"pulDiskNumber";
    goto LABEL_6;
  }
  *a3 = 0;
  v7 = CBaseStringT<unsigned short>::Append((__int64)&v15, (__int64)a2);
  if ( v7 >= 0 )
  {
    v7 = CPathString::TrimBackslash((CPathString *)&v15);
    if ( v7 >= 0 )
    {
      v10 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v15);
      FileW = CreateFileW(v10, 0, 1u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL )
        goto LABEL_32;
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 112;
          goto LABEL_18;
        }
      }
      else
      {
LABEL_32:
        v13 = operator new(0x2800u);
        if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v13, 0x2800u, &BytesReturned, 0) )
          *a3 = v13[2];
        if ( FileW != (HANDLE)-1LL )
          CloseHandle(FileW);
        operator delete(v13);
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 111;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 110;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, (unsigned int)v7);
    }
  }
LABEL_37:
  CPathString::~CPathString((CPathString *)&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800498cc  mov     [rsp-18h+arg_8], rbx
0x1800498d1  mov     [rsp-18h+arg_10], rsi
0x1800498d6  mov     qword ptr [rsp-18h+BytesReturned], rcx
0x1800498db  push    rbp
0x1800498dc  push    rdi
0x1800498dd  push    r14
0x1800498df  mov     rbp, rsp
0x1800498e2  sub     rsp, 70h
0x1800498e6  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800498ed  mov     [rbp+var_24], 80h
0x1800498f5  mov     [rbp+var_30], rax
0x1800498f9  mov     rdi, r8
0x1800498fc  mov     [rbp+var_18], 0
0x180049904  mov     [rbp+var_1C], 0
0x18004990b  mov     [rbp+var_10], 8000000h
0x180049912  mov     [rbp+var_28], 0
0x180049919  mov     [rbp+BytesReturned], 0
0x180049920  test    rdx, rdx
0x180049923  jnz     short loc_18004996A
0x180049925  mov     rcx, cs:WPP_GLOBAL_Control
0x18004992c  lea     rax, WPP_GLOBAL_Control
0x180049933  cmp     rcx, rax
0x180049936  jz      short loc_180049960
0x180049938  test    byte ptr [rcx+1Ch], 1
0x18004993c  jz      short loc_180049960
0x18004993e  cmp     byte ptr [rcx+19h], 2
0x180049942  jb      short loc_180049960
0x180049944  mov     edx, 6Ch ; 'l'
0x180049949  lea     r9, aSzvolumeguidpa; "szVolumeGuidPath"
0x180049950  mov     rcx, [rcx+10h]
0x180049954  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004995b  call    WPP_SF_S
0x180049960  mov     ebx, 80070057h
0x180049965  jmp     loc_180049B19
0x18004996a  test    rdi, rdi
0x18004996d  jnz     short loc_18004999A
0x18004996f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049976  lea     rax, WPP_GLOBAL_Control
0x18004997d  cmp     rcx, rax
0x180049980  jz      short loc_180049960
0x180049982  test    byte ptr [rcx+1Ch], 1
0x180049986  jz      short loc_180049960
0x180049988  cmp     byte ptr [rcx+19h], 2
0x18004998c  jb      short loc_180049960
0x18004998e  lea     edx, [rdi+6Dh]
0x180049991  lea     r9, aPuldisknumber; "pulDiskNumber"
0x180049998  jmp     short loc_180049950
0x18004999a  lea     rcx, [rbp+var_30]
0x18004999e  mov     dword ptr [r8], 0
0x1800499a5  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x1800499aa  mov     ebx, eax
0x1800499ac  test    eax, eax
0x1800499ae  jns     short loc_1800499F8
0x1800499b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499b7  lea     rax, WPP_GLOBAL_Control
0x1800499be  cmp     rcx, rax
0x1800499c1  jz      loc_180049B19
0x1800499c7  test    byte ptr [rcx+1Ch], 1
0x1800499cb  jz      loc_180049B19
0x1800499d1  cmp     byte ptr [rcx+19h], 2
0x1800499d5  jb      loc_180049B19
0x1800499db  mov     edx, 6Eh ; 'n'
0x1800499e0  mov     rcx, [rcx+10h]
0x1800499e4  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x1800499eb  mov     r9d, ebx
0x1800499ee  call    WPP_SF_d
0x1800499f3  jmp     loc_180049B19
0x1800499f8  lea     rcx, [rbp+var_30]; this
0x1800499fc  call    ?TrimBackslash@CPathString@@QEAAJXZ; CPathString::TrimBackslash(void)
0x180049a01  mov     ebx, eax
0x180049a03  test    eax, eax
0x180049a05  jns     short loc_180049A39
0x180049a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a0e  lea     rax, WPP_GLOBAL_Control
0x180049a15  cmp     rcx, rax
0x180049a18  jz      loc_180049B19
0x180049a1e  test    byte ptr [rcx+1Ch], 1
0x180049a22  jz      loc_180049B19
0x180049a28  cmp     byte ptr [rcx+19h], 2
0x180049a2c  jb      loc_180049B19
0x180049a32  mov     edx, 6Fh ; 'o'
0x180049a37  jmp     short loc_1800499E0
0x180049a39  lea     rcx, [rbp+var_30]
0x180049a3d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180049a42  xor     r9d, r9d; lpSecurityAttributes
0x180049a45  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180049a4e  mov     rcx, rax; lpFileName
0x180049a51  mov     [rsp+70h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180049a59  xor     edx, edx; dwDesiredAccess
0x180049a5b  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180049a63  lea     r8d, [r9+1]; dwShareMode
0x180049a67  call    cs:__imp_CreateFileW
0x180049a6d  mov     rsi, rax
0x180049a70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049a74  jnz     short loc_180049AB8
0x180049a76  call    cs:__imp_GetLastError
0x180049a7c  mov     ebx, eax
0x180049a7e  test    eax, eax
0x180049a80  jle     short loc_180049A8B
0x180049a82  movzx   ebx, ax
0x180049a85  or      ebx, 80070000h
0x180049a8b  test    ebx, ebx
0x180049a8d  jns     short loc_180049AB8
0x180049a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a96  lea     rax, WPP_GLOBAL_Control
0x180049a9d  cmp     rcx, rax
0x180049aa0  jz      short loc_180049B19
0x180049aa2  test    byte ptr [rcx+1Ch], 1
0x180049aa6  jz      short loc_180049B19
0x180049aa8  cmp     byte ptr [rcx+19h], 2
0x180049aac  jb      short loc_180049B19
0x180049aae  mov     edx, 70h ; 'p'
0x180049ab3  jmp     loc_1800499E0
0x180049ab8  mov     ecx, 2800h; Size
0x180049abd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049ac2  mov     r14, rax
0x180049ac5  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180049ace  lea     rax, [rbp+BytesReturned]
0x180049ad2  xor     r9d, r9d; nInBufferSize
0x180049ad5  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x180049ada  xor     r8d, r8d; lpInBuffer
0x180049add  mov     [rsp+70h+dwFlagsAndAttributes], 2800h; nOutBufferSize
0x180049ae5  mov     edx, 560000h; dwIoControlCode
0x180049aea  mov     rcx, rsi; hDevice
0x180049aed  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; lpOutBuffer
0x180049af2  call    cs:__imp_DeviceIoControl
0x180049af8  test    eax, eax
0x180049afa  jz      short loc_180049B02
0x180049afc  mov     eax, [r14+8]
0x180049b00  mov     [rdi], eax
0x180049b02  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180049b06  jz      short loc_180049B11
0x180049b08  mov     rcx, rsi; hObject
0x180049b0b  call    cs:__imp_CloseHandle
0x180049b11  mov     rcx, r14; Block
0x180049b14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049b19  lea     rcx, [rbp+var_30]; this
0x180049b1d  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180049b22  lea     r11, [rsp+70h+var_s0]
0x180049b27  mov     eax, ebx
0x180049b29  mov     rbx, [r11+28h]
0x180049b2d  mov     rsi, [r11+30h]
0x180049b31  mov     rsp, r11
0x180049b34  pop     r14
0x180049b36  pop     rdi
0x180049b37  pop     rbp
0x180049b38  retn
```

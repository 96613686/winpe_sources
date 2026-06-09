# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x18001285c`
- end: `0x180012b8c`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `816`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a30c`
- `0x180016ad0`

## callees

- `0x18000139c`
- `0x180001620`
- `0x180011e8c`
- `0x1800126bc`
- `0x18001285c`
- `0x1800132ec`
- `0x180013598`
- `0x180026e30`
- `0x180027334`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001290e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001290e`
- `KERNEL32!FindVolumeClose` at `0x180012ae9`
- `KERNEL32!FindVolumeClose` at `0x180012ae9`
- `KERNEL32!FindNextVolumeW` at `0x180012ad8`
- `KERNEL32!FindNextVolumeW` at `0x180012ad8`
- `KERNEL32!QueryDosDeviceW` at `0x180012a9d`
- `KERNEL32!QueryDosDeviceW` at `0x180012a9d`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180012a15`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180012a15`
- `KERNEL32!FindFirstVolumeW` at `0x1800129d7`
- `KERNEL32!FindFirstVolumeW` at `0x1800129d7`
- `KERNEL32!GetSystemDirectoryW` at `0x1800128c4`
- `KERNEL32!GetSystemDirectoryW` at `0x1800128c4`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rax
  const unsigned __int16 *v5; // r8
  HANDLE FirstVolumeW; // rsi
  int v7; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  WCHAR *v10; // rcx
  bool v11; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-C88h] BYREF
  HANDLE v13; // [rsp+28h] [rbp-C80h]
  __int64 v14; // [rsp+30h] [rbp-C78h]
  WCHAR szVolumeName[4]; // [rsp+40h] [rbp-C68h] BYREF
  char v17; // [rsp+48h] [rbp-C60h] BYREF
  __int16 v18; // [rsp+246h] [rbp-A62h]
  WCHAR Buffer[264]; // [rsp+250h] [rbp-A58h] BYREF
  WCHAR szVolumePathNames[1040]; // [rsp+460h] [rbp-848h] BYREF

  v14 = -2;
  v2 = *((_QWORD *)this + 1);
  if ( v2 != *((_QWORD *)this + 2) )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(
      this,
      *((_QWORD *)this + 1),
      *((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = v2;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  std::wstring::assign((char *)this + 64, Buffer);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &qword_18002BEF8, 0);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
    ATL::AtlThrowLastWin32();
  v3 = -1;
  do
    ++v3;
  while ( Buffer[v3] );
  if ( v3 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v3 - 1] != 92 )
  {
    if ( v3 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v3] = 92;
    v4 = 2 * v3 + 2;
    if ( v4 >= 0x20A )
      _report_rangecheckfailure(Buffer);
    *(WCHAR *)((char *)Buffer + v4) = 0;
  }
  std::wstring::assign((char *)this + 104, Buffer);
  if ( *((_QWORD *)this + 17) < 8u )
    v5 = (const unsigned __int16 *)((char *)this + 112);
  else
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 14);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v5, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v13 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    do
    {
      v18 = 0;
      v7 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v7) = szVolumePathNames[0] != 0;
      v8 = -1;
      do
        ++v8;
      while ( szVolumeName[v8] );
      if ( v8 && szVolumeName[v8 - 1] == 92 )
      {
        v9 = 2 * v8 - 2;
        if ( v9 >= 0x208 )
          _report_rangecheckfailure(szVolumeName);
        *(WCHAR *)((char *)szVolumeName + v9) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v10 = (WCHAR *)&v17, szVolumeName[3] != 92) )
      {
        v10 = szVolumeName;
      }
      if ( QueryDosDeviceW(v10, Buffer, 0x104u) )
      {
        if ( v7 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer, v11);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v13);
    throw;
  }
  FindVolumeClose(FirstVolumeW);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\Device\\LanmanRedirector\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\Mup\\", L"\\\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\vmsmb\\", L"\\\\?\\VMSMB\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\\\", L"\\\\", 0);
  *((_BYTE *)this + 144) = 1;
}

```

## disassembly

```asm
0x18001285c  mov     rax, rsp
0x18001285f  push    r12
0x180012861  push    r13
0x180012863  push    r15
0x180012865  sub     rsp, 0C90h
0x18001286c  mov     [rsp+0CA8h+var_C78], 0FFFFFFFFFFFFFFFEh
0x180012875  mov     [rax+10h], rbx
0x180012879  mov     [rax+18h], rsi
0x18001287d  mov     [rax+20h], rdi
0x180012881  mov     rax, cs:__security_cookie
0x180012888  xor     rax, rsp
0x18001288b  mov     [rsp+0CA8h+var_28], rax
0x180012893  mov     rdi, rcx
0x180012896  mov     rsi, [rcx+10h]
0x18001289a  mov     rbx, [rcx+8]
0x18001289e  cmp     rbx, rsi
0x1800128a1  jz      short loc_1800128B3
0x1800128a3  mov     r8, [rcx+10h]
0x1800128a7  mov     rdx, rbx
0x1800128aa  call    ?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)
0x1800128af  mov     [rdi+10h], rbx
0x1800128b3  mov     r13d, 104h
0x1800128b9  mov     edx, r13d; uSize
0x1800128bc  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x1800128c4  call    cs:__imp_GetSystemDirectoryW
0x1800128ca  xor     r15d, r15d
0x1800128cd  test    eax, eax
0x1800128cf  jnz     short loc_1800128D7
0x1800128d1  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800128d7  lea     rcx, [rdi+40h]
0x1800128db  lea     rdx, [rsp+0CA8h+Buffer]
0x1800128e3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800128e8  xor     r9d, r9d; bool
0x1800128eb  lea     r8, qword_18002BEF8; unsigned __int16 *
0x1800128f2  lea     rdx, asc_18002CD48; "\\??\\"
0x1800128f9  mov     rcx, rdi; this
0x1800128fc  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012901  mov     edx, 105h; uSize
0x180012906  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x18001290e  call    cs:__imp_GetSystemWindowsDirectoryW
0x180012914  test    eax, eax
0x180012916  jnz     short loc_18001291E
0x180012918  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18001291e  lea     rcx, [rsp+0CA8h+Buffer]
0x180012926  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001292a  inc     rax
0x18001292d  cmp     [rcx+rax*2], r15w
0x180012932  jnz     short loc_18001292A
0x180012934  cmp     rax, 2
0x180012938  jb      loc_180012B53
0x18001293e  cmp     [rsp+0CA8h+var_A56], 3Ah ; ':'
0x180012947  jnz     loc_180012B53
0x18001294d  mov     r12d, 5Ch ; '\'
0x180012953  cmp     [rsp+rax*2+0CA8h+var_A5A], r12w
0x18001295c  jz      short loc_180012998
0x18001295e  cmp     rax, r13
0x180012961  jnb     short loc_18001298D
0x180012963  mov     [rsp+rax*2+0CA8h+Buffer], r12w
0x18001296c  lea     rax, ds:2[rax*2]
0x180012974  cmp     rax, 20Ah
0x18001297a  jnb     short loc_180012987
0x18001297c  mov     [rsp+rax+0CA8h+Buffer], r15w
0x180012985  jmp     short loc_180012998
0x180012987  call    __report_rangecheckfailure
0x18001298d  mov     ecx, 8007007Ah; int
0x180012992  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012998  lea     rdx, [rsp+0CA8h+Buffer]
0x1800129a0  lea     rcx, [rdi+68h]
0x1800129a4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800129a9  cmp     qword ptr [rdi+88h], 8
0x1800129b1  jb      short loc_1800129B9
0x1800129b3  mov     r8, [rdi+70h]
0x1800129b7  jmp     short loc_1800129BD
0x1800129b9  lea     r8, [rdi+70h]; unsigned __int16 *
0x1800129bd  mov     r9b, 1; bool
0x1800129c0  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x1800129c7  mov     rcx, rdi; this
0x1800129ca  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800129cf  mov     edx, r13d; cchBufferLength
0x1800129d2  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x1800129d7  call    cs:__imp_FindFirstVolumeW
0x1800129dd  mov     rsi, rax
0x1800129e0  mov     [rsp+0CA8h+var_C80], rax
0x1800129e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800129e9  jnz     short loc_1800129F1
0x1800129eb  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800129f1  mov     [rsp+0CA8h+var_A62], r15w
0x1800129fa  mov     ebx, r15d
0x1800129fd  lea     r9, [rsp+0CA8h+cchReturnLength]; lpcchReturnLength
0x180012a02  mov     r8d, 410h; cchBufferLength
0x180012a08  lea     rdx, [rsp+0CA8h+szVolumePathNames]; lpszVolumePathNames
0x180012a10  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180012a15  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180012a1b  test    eax, eax
0x180012a1d  jz      short loc_180012A2B
0x180012a1f  cmp     [rsp+0CA8h+szVolumePathNames], r15w
0x180012a28  setnz   bl
0x180012a2b  lea     rcx, [rsp+0CA8h+szVolumeName]
0x180012a30  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a34  inc     rax
0x180012a37  cmp     [rcx+rax*2], r15w
0x180012a3c  jnz     short loc_180012A34
0x180012a3e  test    rax, rax
0x180012a41  jz      short loc_180012A68
0x180012a43  cmp     [rsp+rax*2+0CA8h+var_C6A], r12w
0x180012a49  jnz     short loc_180012A68
0x180012a4b  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180012a53  cmp     rax, 208h
0x180012a59  jnb     short loc_180012A63
0x180012a5b  mov     [rsp+rax+0CA8h+szVolumeName], r15w
0x180012a61  jmp     short loc_180012A68
0x180012a63  call    __report_rangecheckfailure
0x180012a68  cmp     [rsp+0CA8h+szVolumeName], r12w
0x180012a6e  jnz     short loc_180012A8D
0x180012a70  cmp     [rsp+0CA8h+var_C66], r12w
0x180012a76  jnz     short loc_180012A8D
0x180012a78  cmp     [rsp+0CA8h+var_C64], 3Fh ; '?'
0x180012a7e  jnz     short loc_180012A8D
0x180012a80  cmp     [rsp+0CA8h+var_C62], r12w
0x180012a86  lea     rcx, [rsp+0CA8h+var_C60]
0x180012a8b  jz      short loc_180012A92
0x180012a8d  lea     rcx, [rsp+0CA8h+szVolumeName]; lpDeviceName
0x180012a92  mov     r8d, r13d; ucchMax
0x180012a95  lea     rdx, [rsp+0CA8h+Buffer]; lpTargetPath
0x180012a9d  call    cs:__imp_QueryDosDeviceW
0x180012aa3  test    eax, eax
0x180012aa5  jz      short loc_180012ACD
0x180012aa7  lea     rdx, [rsp+0CA8h+Buffer]; unsigned __int16 *
0x180012aaf  mov     rcx, rdi; this
0x180012ab2  test    ebx, ebx
0x180012ab4  jz      short loc_180012AC8
0x180012ab6  mov     r9b, 1; bool
0x180012ab9  lea     r8, [rsp+0CA8h+szVolumePathNames]; unsigned __int16 *
0x180012ac1  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012ac6  jmp     short loc_180012ACD
0x180012ac8  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x180012acd  mov     r8d, r13d; cchBufferLength
0x180012ad0  lea     rdx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180012ad5  mov     rcx, rsi; hFindVolume
0x180012ad8  call    cs:__imp_FindNextVolumeW
0x180012ade  test    eax, eax
0x180012ae0  jnz     loc_1800129F1
0x180012ae6  mov     rcx, rsi; hFindVolume
0x180012ae9  call    cs:__imp_FindVolumeClose
0x180012aef  xor     r9d, r9d; bool
0x180012af2  lea     rbx, asc_18002CE08; "\\\\"
0x180012af9  mov     r8, rbx; unsigned __int16 *
0x180012afc  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180012b03  mov     rcx, rdi; this
0x180012b06  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b0b  xor     r9d, r9d; bool
0x180012b0e  mov     r8, rbx; unsigned __int16 *
0x180012b11  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180012b18  mov     rcx, rdi; this
0x180012b1b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b20  xor     r9d, r9d; bool
0x180012b23  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180012b2a  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180012b31  mov     rcx, rdi; this
0x180012b34  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b39  xor     r9d, r9d; bool
0x180012b3c  mov     r8, rbx; unsigned __int16 *
0x180012b3f  mov     rdx, rbx; unsigned __int16 *
0x180012b42  mov     rcx, rdi; this
0x180012b45  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b4a  mov     byte ptr [rdi+90h], 1
0x180012b51  jmp     short loc_180012B5E
0x180012b53  mov     ecx, 8000FFFFh; int
0x180012b58  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012b5e  mov     rcx, [rsp+0CA8h+var_28]
0x180012b66  xor     rcx, rsp; StackCookie
0x180012b69  call    __security_check_cookie
0x180012b6e  lea     r11, [rsp+0CA8h+var_18]
0x180012b76  mov     rbx, [r11+28h]
0x180012b7a  mov     rsi, [r11+30h]
0x180012b7e  mov     rdi, [r11+38h]
0x180012b82  mov     rsp, r11
0x180012b85  pop     r15
0x180012b87  pop     r13
0x180012b89  pop     r12
0x180012b8b  retn
```

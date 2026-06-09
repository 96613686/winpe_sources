# _anonymous_namespace_::TempCleanup::IsDiskCleanupEligible

- ea: `0x1800241e4`
- end: `0x180024362`
- name: `_anonymous_namespace_::TempCleanup::IsDiskCleanupEligible`
- size: `382`
- prototype: `HRESULT __fastcall(bool *eligible)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024138`

## callees

- `0x1800022b0`
- `0x180009778`
- `0x1800241e4`
- `0x1800259d8`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002420c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002420c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002429a`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002429a`

## string_xrefs

- `0x180024231`: `GetSystemDirectoryW %u`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::TempCleanup::IsDiskCleanupEligible(bool *eligible)
{
  UINT SystemDirectoryW; // eax
  bool v4; // r8
  double LowPart; // xmm1_8
  double v6; // xmm0_8
  _ULARGE_INTEGER cbFree; // [rsp+30h] [rbp-238h] BYREF
  _ULARGE_INTEGER cbTotal; // [rsp+38h] [rbp-230h] BYREF
  wchar_t wzSystemDirectory[264]; // [rsp+40h] [rbp-228h] BYREF
  void *retaddr; // [rsp+268h] [rbp+0h]

  SystemDirectoryW = GetSystemDirectoryW(wzSystemDirectory, 0x104u);
  if ( SystemDirectoryW < 0x104 )
  {
    if ( 2 * (unsigned __int64)SystemDirectoryW >= 0x208 )
      _report_rangecheckfailure();
    wzSystemDirectory[SystemDirectoryW] = 0;
    cbFree.QuadPart = 0;
    cbTotal.QuadPart = 0;
    if ( GetDiskFreeSpaceExW(wzSystemDirectory, 0, &cbTotal, &cbFree) )
    {
      v4 = 1;
      if ( (cbFree.QuadPart & 0x8000000000000000uLL) != 0LL )
        LowPart = (double)(int)(cbFree.LowPart & 1 | (cbFree.QuadPart >> 1))
                + (double)(int)(cbFree.LowPart & 1 | (cbFree.QuadPart >> 1));
      else
        LowPart = (double)(int)cbFree.LowPart;
      if ( (cbTotal.QuadPart & 0x8000000000000000uLL) != 0LL )
        v6 = (double)(int)(cbTotal.LowPart & 1 | (cbTotal.QuadPart >> 1))
           + (double)(int)(cbTotal.LowPart & 1 | (cbTotal.QuadPart >> 1));
      else
        v6 = (double)(int)cbTotal.LowPart;
      if ( LowPart / v6 > 0.2 || cbFree.QuadPart > 0x640000000LL )
        v4 = 0;
      *eligible = v4;
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastErrorMsg(
               retaddr,
               0x162u,
               "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
               "GetDiskFreeSpaceExW %ws",
               wzSystemDirectory);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x15Au,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
      -2147024774,
      "GetSystemDirectoryW %u",
      SystemDirectoryW);
    return -2147024774;
  }
}

```

## disassembly

```asm
0x1800241e4  push    rbx
0x1800241e6  sub     rsp, 260h
0x1800241ed  mov     rax, cs:__security_cookie
0x1800241f4  xor     rax, rsp
0x1800241f7  mov     [rsp+268h+var_18], rax
0x1800241ff  mov     rbx, eligible
0x180024202  mov     edx, 104h; uSize
0x180024207  lea     eligible, [rsp+268h+wzSystemDirectory]; lpBuffer
0x18002420c  call    cs:__imp_GetSystemDirectoryW
0x180024212  cmp     eax, 104h
0x180024217  jb      short loc_180024265
0x180024219  mov     eligible, [rsp+268h]; callerReturnAddress
0x180024221  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024228  mov     [rsp+268h+var_240], eax
0x18002422c  mov     ebx, 8007007Ah
0x180024231  lea     rax, aGetsystemdirec; "GetSystemDirectoryW %u"
0x180024238  mov     r9d, ebx; hr
0x18002423b  mov     edx, 15Ah; lineNumber
0x180024240  mov     [rsp+268h+formatString], rax; formatString
0x180024245  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002424a  mov     eax, ebx
0x18002424c  mov     eligible, [rsp+268h+var_18]
0x180024254  xor     eligible, rsp; StackCookie
0x180024257  call    __security_check_cookie
0x18002425c  add     rsp, 260h
0x180024263  pop     rbx
0x180024264  retn
0x180024265  mov     eax, eax
0x180024267  lea     eligible, [rax+rax]
0x18002426b  cmp     eligible, 208h
0x180024272  jnb     loc_18002435C
0x180024278  xor     eax, eax
0x18002427a  lea     r9, [rsp+268h+cbFree]; lpTotalNumberOfFreeBytes
0x18002427f  mov     [rsp+eligible+268h+wzSystemDirectory], ax
0x180024284  lea     r8, [rsp+268h+cbTotal]; lpTotalNumberOfBytes
0x180024289  lea     eligible, [rsp+268h+wzSystemDirectory]; lpDirectoryName
0x18002428e  mov     qword ptr [rsp+268h+cbFree], rax
0x180024293  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180024295  mov     qword ptr [rsp+268h+cbTotal], rax
0x18002429a  call    cs:__imp_GetDiskFreeSpaceExW
0x1800242a0  test    eax, eax
0x1800242a2  jnz     short loc_1800242D3
0x1800242a4  mov     eligible, [rsp+268h]; callerReturnAddress
0x1800242ac  lea     rax, [rsp+268h+wzSystemDirectory]
0x1800242b1  lea     r9, aGetdiskfreespa; "GetDiskFreeSpaceExW %ws"
0x1800242b8  mov     [rsp+268h+formatString], rax
0x1800242bd  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800242c4  mov     edx, 162h; lineNumber
0x1800242c9  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800242ce  jmp     loc_18002424C
0x1800242d3  mov     rax, qword ptr [rsp+268h+cbFree]
0x1800242d8  mov     r8d, 1
0x1800242de  xorps   xmm1, xmm1
0x1800242e1  test    rax, rax
0x1800242e4  js      short loc_1800242ED
0x1800242e6  cvtsi2sd xmm1, rax
0x1800242eb  jmp     short loc_180024305
0x1800242ed  mov     rdx, rax
0x1800242f0  mov     eligible, rax
0x1800242f3  shr     rdx, 1
0x1800242f6  and     eligible, r8
0x1800242f9  or      rdx, eligible
0x1800242fc  cvtsi2sd xmm1, rdx
0x180024301  addsd   xmm1, xmm1
0x180024305  mov     rdx, qword ptr [rsp+268h+cbTotal]
0x18002430a  xorps   xmm0, xmm0
0x18002430d  test    rdx, rdx
0x180024310  js      short loc_180024319
0x180024312  cvtsi2sd xmm0, rdx
0x180024317  jmp     short loc_18002432E
0x180024319  mov     eligible, rdx
0x18002431c  and     rdx, r8
0x18002431f  shr     eligible, 1
0x180024322  or      eligible, rdx
0x180024325  cvtsi2sd xmm0, eligible
0x18002432a  addsd   xmm0, xmm0
0x18002432e  divsd   xmm1, xmm0
0x180024332  movsd   xmm0, cs:__real@3fc999999999999a
0x18002433a  comisd  xmm0, xmm1
0x18002433e  jb      short loc_18002434F
0x180024340  mov     eligible, 640000000h
0x18002434a  cmp     rax, eligible
0x18002434d  jbe     short loc_180024352
0x18002434f  xor     r8b, r8b
0x180024352  mov     [rbx], r8b
0x180024355  xor     eax, eax
0x180024357  jmp     loc_18002424C
0x18002435c  call    __report_rangecheckfailure
```

# Region::Region(Windows::Globalization::IGeographicRegion &)

- ea: `0x180037890`
- end: `0x1800379b2`
- name: `??0Region@@QEAA@AEAUIGeographicRegion@Globalization@Windows@@@Z`
- size: `290`
- prototype: `Region *__fastcall(Region *__hidden this, struct Windows::Globalization::IGeographicRegion *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800379b8`

## callees

- `0x180006ee0`
- `0x180007ed9`
- `0x18000ecc0`
- `0x1800157f8`
- `0x180035e0c`
- `0x180037890`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800378cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800378cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800378f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800378f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Region *__fastcall Region::Region(Region *this, struct Windows::Globalization::IGeographicRegion *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Globalization::IGeographicRegion *, HSTRING *); // rbx
  int v5; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  Region *v9; // rdi
  __int64 v10; // rbx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+78h] [rbp+10h] BYREF

  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 7;
  *(_WORD *)this = 0;
  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Globalization::IGeographicRegion *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_c3f17ae399943b49d0ae14f2891266f3_Traceguids,
        (unsigned int)v5);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v8 = -1;
  do
    ++v8;
  while ( StringRawBuffer[v8] );
  if ( v8 > *((_QWORD *)this + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      this,
      v8,
      v7,
      StringRawBuffer);
  }
  else
  {
    if ( *((_QWORD *)this + 3) <= 7u )
      v9 = this;
    else
      v9 = *(Region **)this;
    *((_QWORD *)this + 2) = v8;
    v10 = 2 * v8;
    memmove_0(v9, StringRawBuffer, 2 * v8);
    *(_WORD *)((char *)v9 + v10) = 0;
  }
  WindowsDeleteString(string);
  return this;
}

```

## disassembly

```asm
0x180037890  mov     [rsp+arg_10], rbx
0x180037895  mov     [rsp+arg_0], rcx
0x18003789a  push    rbp
0x18003789b  push    rsi
0x18003789c  push    rdi
0x18003789d  sub     rsp, 50h
0x1800378a1  mov     rdi, rdx
0x1800378a4  mov     rsi, rcx
0x1800378a7  xorps   xmm0, xmm0
0x1800378aa  movups  xmmword ptr [rcx], xmm0
0x1800378ad  xor     ebp, ebp
0x1800378af  mov     [rcx+10h], rbp
0x1800378b3  mov     qword ptr [rcx+18h], 7
0x1800378bb  mov     [rcx], bp
0x1800378be  mov     [rsp+68h+string], rbp
0x1800378c3  mov     rax, [rdx]
0x1800378c6  mov     rbx, [rax+30h]
0x1800378ca  xor     ecx, ecx; string
0x1800378cc  call    cs:__imp_WindowsDeleteString
0x1800378d2  mov     [rsp+68h+string], rbp
0x1800378d7  lea     rdx, [rsp+68h+string]
0x1800378dc  mov     rcx, rdi
0x1800378df  mov     rax, rbx
0x1800378e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378e7  mov     ebx, eax
0x1800378e9  test    eax, eax
0x1800378eb  js      short loc_180037963
0x1800378ed  xor     edx, edx; length
0x1800378ef  mov     rcx, [rsp+68h+string]; string
0x1800378f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800378fa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800378fe  inc     rdx
0x180037901  cmp     [rax+rdx*2], bp
0x180037905  jnz     short loc_1800378FE
0x180037907  cmp     rdx, [rsi+18h]
0x18003790b  ja      short loc_180037938
0x18003790d  cmp     qword ptr [rsi+18h], 7
0x180037912  jbe     short loc_180037919
0x180037914  mov     rdi, [rsi]
0x180037917  jmp     short loc_18003791C
0x180037919  mov     rdi, rsi
0x18003791c  mov     [rsi+10h], rdx
0x180037920  lea     rbx, [rdx+rdx]
0x180037924  mov     r8, rbx; Size
0x180037927  mov     rdx, rax; Src
0x18003792a  mov     rcx, rdi; void *
0x18003792d  call    memmove_0
0x180037932  mov     [rbx+rdi], bp
0x180037936  jmp     short loc_180037944
0x180037938  mov     r9, rax
0x18003793b  mov     rcx, rsi
0x18003793e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180037943  nop
0x180037944  mov     rcx, [rsp+68h+string]; string
0x180037949  call    cs:__imp_WindowsDeleteString
0x18003794f  nop
0x180037950  mov     rax, rsi
0x180037953  mov     rbx, [rsp+68h+arg_10]
0x18003795b  add     rsp, 50h
0x18003795f  pop     rdi
0x180037960  pop     rsi
0x180037961  pop     rbp
0x180037962  retn
0x180037963  lea     rax, WPP_GLOBAL_Control
0x18003796a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037971  cmp     rcx, rax
0x180037974  jz      short loc_180037994
0x180037976  test    byte ptr [rcx+1Ch], 1
0x18003797a  jz      short loc_180037994
0x18003797c  mov     edx, 0Eh
0x180037981  mov     r9d, ebx
0x180037984  lea     r8, WPP_c3f17ae399943b49d0ae14f2891266f3_Traceguids
0x18003798b  mov     rcx, [rcx+10h]
0x18003798f  call    WPP_SF_d
0x180037994  mov     edx, ebx; int
0x180037996  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18003799b  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800379a0  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800379a7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800379ac  call    _CxxThrowException_0
```

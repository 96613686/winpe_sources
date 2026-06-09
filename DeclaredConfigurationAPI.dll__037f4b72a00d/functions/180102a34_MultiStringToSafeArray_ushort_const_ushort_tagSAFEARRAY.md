# MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)

- ea: `0x180102a34`
- end: `0x180102b96`
- name: `?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(OLECHAR *strIn, unsigned __int16, struct tagSAFEARRAY **)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180076c10`
- `0x180078e2c`
- `0x18007f370`
- `0x180081a94`
- `0x1800ad2b4`
- `0x1800b7b20`
- `0x1800baf74`
- `0x1800c0f2c`
- `0x1800c4fe4`
- `0x1800ca3c4`
- `0x1800d0ae0`
- `0x1800e290c`
- `0x180110328`
- `0x18011440c`
- `0x1801247b4`

## callees

- `0x180102a34`
- `0x180105984`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180102b1a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180102b1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180102b60`
- `OLEAUT32!__imp_SysFreeString` at `0x180102b60`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180102a81`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180102aca`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180102a81`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180102aca`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180102b7d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180102b7d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102adf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102adf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102b48`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102b74`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102b48`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102b74`

## pseudocode

```c
__int64 __fastcall MultiStringToSafeArray(OLECHAR *strIn, __int64 a2, struct tagSAFEARRAY **a3)
{
  OLECHAR *v4; // rsi
  SAFEARRAY *v5; // rdi
  HRESULT v6; // ebx
  ULONG cElements; // edx
  OLECHAR *v8; // rax
  SAFEARRAY *v10; // rax
  ULONG i; // ebx
  const OLECHAR *v12; // rcx
  bool v13; // zf
  BSTR v14; // rax
  __int64 v15; // rdx
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+30h] BYREF
  void *ppvData; // [rsp+68h] [rbp+48h] BYREF

  ppvData = 0;
  v4 = strIn;
  rgsabound = 0;
  v5 = 0;
  if ( !strIn || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_28;
  }
  if ( !*strIn )
  {
    v5 = SafeArrayCreate(8u, 1u, &rgsabound);
    if ( !v5 )
    {
LABEL_6:
      v6 = -2147024882;
      goto LABEL_28;
    }
    v6 = 0;
    goto LABEL_27;
  }
  cElements = rgsabound.cElements;
  v8 = strIn;
  do
  {
    ++cElements;
    while ( *v8++ )
      ;
  }
  while ( *v8 );
  rgsabound.cElements = cElements;
  v10 = SafeArrayCreate(8u, 1u, &rgsabound);
  v5 = v10;
  if ( !v10 )
    goto LABEL_6;
  v6 = SafeArrayAccessData(v10, &ppvData);
  if ( v6 >= 0 )
  {
    if ( !ppvData )
      ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    for ( i = 0; ; ++i )
    {
      v12 = v4;
      v13 = i == rgsabound.cElements;
      if ( i >= rgsabound.cElements )
        break;
      if ( !*v4 )
      {
        v13 = i == rgsabound.cElements;
        break;
      }
      do
        ++v4;
      while ( *v4 );
      v14 = SysAllocStringLen(v12, v4 - v12);
      if ( !v14 )
        goto LABEL_6;
      ++v4;
      v15 = i;
      *((_QWORD *)ppvData + v15) = v14;
    }
    if ( !v13 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    v6 = SafeArrayUnaccessData(v5);
    if ( v6 >= 0 )
    {
      ppvData = 0;
LABEL_27:
      *a3 = v5;
      v5 = 0;
    }
  }
LABEL_28:
  SysFreeString(0);
  if ( v5 )
  {
    if ( ppvData )
      SafeArrayUnaccessData(v5);
    SafeArrayDestroy(v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180102a34  mov     [rsp-28h+arg_8], rbx
0x180102a39  push    rbp
0x180102a3a  push    rsi
0x180102a3b  push    rdi
0x180102a3c  push    r14
0x180102a3e  push    r15
0x180102a40  mov     rbp, rsp
0x180102a43  sub     rsp, 20h
0x180102a47  xor     r15d, r15d
0x180102a4a  mov     r14, r8
0x180102a4d  mov     [rbp+ppvData], r15
0x180102a51  mov     rsi, rcx
0x180102a54  mov     qword ptr [rbp+rgsabound.cElements], r15
0x180102a58  mov     edi, r15d
0x180102a5b  test    rcx, rcx
0x180102a5e  jnz     short loc_180102A6A
0x180102a60  mov     ebx, 80070057h
0x180102a65  jmp     loc_180102B5E
0x180102a6a  test    r14, r14
0x180102a6d  jz      short loc_180102A60
0x180102a6f  cmp     r15w, [rcx]
0x180102a73  jnz     short loc_180102AA1
0x180102a75  mov     ecx, 8; vt
0x180102a7a  lea     r8, [rbp+rgsabound]; rgsabound
0x180102a7e  lea     edx, [rcx-7]; cDims
0x180102a81  call    cs:__imp_SafeArrayCreate
0x180102a87  mov     rdi, rax
0x180102a8a  test    rax, rax
0x180102a8d  jnz     short loc_180102A99
0x180102a8f  mov     ebx, 8007000Eh
0x180102a94  jmp     loc_180102B5E
0x180102a99  mov     ebx, r15d
0x180102a9c  jmp     loc_180102B58
0x180102aa1  mov     edx, [rbp+rgsabound.cElements]
0x180102aa4  mov     rax, rsi
0x180102aa7  inc     edx
0x180102aa9  movzx   ecx, word ptr [rax]
0x180102aac  add     rax, 2
0x180102ab0  test    cx, cx
0x180102ab3  jnz     short loc_180102AA9
0x180102ab5  cmp     [rax], r15w
0x180102ab9  jnz     short loc_180102AA7
0x180102abb  mov     ecx, 8; vt
0x180102ac0  mov     [rbp+rgsabound.cElements], edx
0x180102ac3  lea     r8, [rbp+rgsabound]; rgsabound
0x180102ac7  lea     edx, [rcx-7]; cDims
0x180102aca  call    cs:__imp_SafeArrayCreate
0x180102ad0  mov     rdi, rax
0x180102ad3  test    rax, rax
0x180102ad6  jz      short loc_180102A8F
0x180102ad8  lea     rdx, [rbp+ppvData]; ppvData
0x180102adc  mov     rcx, rax; psa
0x180102adf  call    cs:__imp_SafeArrayAccessData
0x180102ae5  mov     ebx, eax
0x180102ae7  test    eax, eax
0x180102ae9  js      short loc_180102B5E
0x180102aeb  cmp     [rbp+ppvData], r15
0x180102aef  jnz     short loc_180102AF6
0x180102af1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102af6  mov     ebx, r15d
0x180102af9  mov     rcx, rsi; strIn
0x180102afc  cmp     ebx, [rbp+rgsabound.cElements]
0x180102aff  jnb     short loc_180102B3E
0x180102b01  cmp     [rsi], r15w
0x180102b05  jz      short loc_180102B3B
0x180102b07  add     rsi, 2
0x180102b0b  cmp     [rsi], r15w
0x180102b0f  jnz     short loc_180102B07
0x180102b11  mov     rdx, rsi
0x180102b14  sub     rdx, rcx
0x180102b17  sar     rdx, 1; ui
0x180102b1a  call    cs:__imp_SysAllocStringLen
0x180102b20  test    rax, rax
0x180102b23  jz      loc_180102A8F
0x180102b29  mov     rcx, [rbp+ppvData]
0x180102b2d  add     rsi, 2
0x180102b31  mov     edx, ebx
0x180102b33  inc     ebx
0x180102b35  mov     [rcx+rdx*8], rax
0x180102b39  jmp     short loc_180102AF9
0x180102b3b  cmp     ebx, [rbp+rgsabound.cElements]
0x180102b3e  jz      short loc_180102B45
0x180102b40  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102b45  mov     rcx, rdi; psa
0x180102b48  call    cs:__imp_SafeArrayUnaccessData
0x180102b4e  mov     ebx, eax
0x180102b50  test    eax, eax
0x180102b52  js      short loc_180102B5E
0x180102b54  mov     [rbp+ppvData], r15
0x180102b58  mov     [r14], rdi
0x180102b5b  mov     rdi, r15
0x180102b5e  xor     ecx, ecx; bstrString
0x180102b60  call    cs:__imp_SysFreeString
0x180102b66  test    rdi, rdi
0x180102b69  jz      short loc_180102B83
0x180102b6b  cmp     [rbp+ppvData], r15
0x180102b6f  jz      short loc_180102B7A
0x180102b71  mov     rcx, rdi; psa
0x180102b74  call    cs:__imp_SafeArrayUnaccessData
0x180102b7a  mov     rcx, rdi; psa
0x180102b7d  call    cs:__imp_SafeArrayDestroy
0x180102b83  mov     eax, ebx
0x180102b85  mov     rbx, [rsp+20h+arg_8]
0x180102b8a  add     rsp, 20h
0x180102b8e  pop     r15
0x180102b90  pop     r14
0x180102b92  pop     rdi
0x180102b93  pop     rsi
0x180102b94  pop     rbp
0x180102b95  retn
```

# WdipWriteParameterCollectionToMessageBuffer

- ea: `0x1800099bc`
- end: `0x180009b36`
- name: `WdipWriteParameterCollectionToMessageBuffer`
- size: `378`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001100`
- `0x180011580`
- `0x1800118f0`
- `0x180011c6c`
- `0x180012934`

## callees

- `0x180009090`
- `0x1800099bc`
- `0x180018370`

## string_xrefs

- `0x180009a01`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180009b0c`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800099fa`: `WdipWriteParameterCollectionToMessageBuffer`
- `0x180009b05`: `WdipWriteParameterCollectionToMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterCollectionToMessageBuffer(__int64 a1, unsigned __int64 a2, unsigned int a3)
{
  int v6; // ebx
  int v7; // r8d
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  int v10; // r8d
  int v11; // r14d
  __int64 i; // rbp
  __int64 v13; // r12
  int Args; // [rsp+20h] [rbp-38h]
  unsigned __int8 *v16; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v6 = -2147024809;
    Args = 87;
    v7 = 621;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipWriteParameterCollectionToMessageBuffer",
      v7,
      (const wchar_t *)L"Error = %d",
      Args);
    return (unsigned int)v6;
  }
  v8 = a2 + *(unsigned int *)(a2 + 124) + 40LL;
  if ( !v8 )
  {
    v6 = -2147024882;
    Args = 14;
    v7 = 623;
    goto LABEL_3;
  }
  if ( v8 < a2 || v8 - a2 > a3 || a2 + a3 - v8 < 4 )
  {
    v10 = 629;
    goto LABEL_19;
  }
  v9 = v8 + 4;
  if ( !v9 || v9 < a2 || v9 - a2 > a3 || a2 + a3 - v9 < 4 )
  {
    v10 = 636;
LABEL_19:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipWriteParameterCollectionToMessageBuffer",
      v10,
      (const wchar_t *)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  v6 = 0;
  v11 = 0;
  v16 = (unsigned __int8 *)(v9 + 4);
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); v11 += *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v13)
                                                                       + 32LL) )
  {
    v13 = (unsigned int)i;
    v6 = WdipWriteParameterToMessageBuffer(
           *(struct __WDIP_PARAMETER **)(*(_QWORD *)(a1 + 8) + 8 * i),
           (struct _DPS_MESSAGE *)a2,
           a3,
           &v16);
    if ( v6 < 0 )
      break;
    i = (unsigned int)(i + 1);
  }
  v16 = (unsigned __int8 *)(a2 + *(unsigned int *)(a2 + 124) + 40LL);
  *(_DWORD *)v16 = i;
  *((_DWORD *)v16 + 1) = v11;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800099bc  mov     [rsp+arg_8], rbx
0x1800099c1  mov     [rsp+arg_10], rbp
0x1800099c6  push    rsi
0x1800099c7  push    rdi
0x1800099c8  push    r12
0x1800099ca  push    r14
0x1800099cc  push    r15
0x1800099ce  sub     rsp, 30h
0x1800099d2  mov     r15d, r8d
0x1800099d5  mov     rdi, rdx
0x1800099d8  mov     rsi, rcx
0x1800099db  test    rcx, rcx
0x1800099de  jnz     short loc_180009A12
0x1800099e0  mov     ebx, 80070057h
0x1800099e5  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800099ed  mov     r8d, 26Dh; int
0x1800099f3  lea     r9, aErrorD; "Error = %d"
0x1800099fa  lea     rdx, aWdipwriteparam_1; "WdipWriteParameterCollectionToMessageBu"...
0x180009a01  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009a08  call    WdipTraceError
0x180009a0d  jmp     loc_180009B1D
0x180009a12  mov     edx, [rdx+7Ch]
0x180009a15  add     rdx, 28h ; '('
0x180009a19  add     rdx, rdi
0x180009a1c  jnz     short loc_180009A33
0x180009a1e  mov     ebx, 8007000Eh
0x180009a23  mov     dword ptr [rsp+58h+Args], 0Eh
0x180009a2b  mov     r8d, 26Fh
0x180009a31  jmp     short loc_1800099F3
0x180009a33  cmp     rdx, rdi
0x180009a36  jb      loc_180009AF0
0x180009a3c  mov     rax, rdx
0x180009a3f  mov     rcx, r15
0x180009a42  sub     rax, rdi
0x180009a45  cmp     rax, r15
0x180009a48  ja      loc_180009AF0
0x180009a4e  mov     rax, rcx
0x180009a51  sub     rax, rdx
0x180009a54  add     rax, rdi
0x180009a57  cmp     rax, 4
0x180009a5b  jb      loc_180009AF0
0x180009a61  add     rdx, 4
0x180009a65  jz      short loc_180009A77
0x180009a67  cmp     rdx, rdi
0x180009a6a  jb      short loc_180009A77
0x180009a6c  mov     rax, rdx
0x180009a6f  sub     rax, rdi
0x180009a72  cmp     rax, rcx
0x180009a75  jbe     short loc_180009A7F
0x180009a77  mov     r8d, 27Ch
0x180009a7d  jmp     short loc_180009AF6
0x180009a7f  sub     rcx, rdx
0x180009a82  add     rcx, rdi
0x180009a85  cmp     rcx, 4
0x180009a89  jb      short loc_180009A77
0x180009a8b  xor     ebx, ebx
0x180009a8d  lea     rax, [rdx+4]
0x180009a91  xor     r14d, r14d
0x180009a94  mov     [rsp+58h+arg_0], rax
0x180009a99  xor     ebp, ebp
0x180009a9b  cmp     [rsi+4], ebx
0x180009a9e  jbe     short loc_180009AD4
0x180009aa0  mov     rcx, [rsi+8]
0x180009aa4  lea     r9, [rsp+58h+arg_0]; unsigned __int8 **
0x180009aa9  mov     r8d, r15d; unsigned int
0x180009aac  mov     r12d, ebp
0x180009aaf  mov     rdx, rdi; struct _DPS_MESSAGE *
0x180009ab2  mov     rcx, [rcx+rbp*8]; struct __WDIP_PARAMETER *
0x180009ab6  call    ?WdipWriteParameterToMessageBuffer@@YAJPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@KPEAPEAE@Z; WdipWriteParameterToMessageBuffer(__WDIP_PARAMETER *,_DPS_MESSAGE *,ulong,uchar * *)
0x180009abb  mov     ebx, eax
0x180009abd  test    eax, eax
0x180009abf  js      short loc_180009AD4
0x180009ac1  mov     rcx, [rsi+8]
0x180009ac5  inc     ebp
0x180009ac7  mov     rdx, [rcx+r12*8]
0x180009acb  add     r14d, [rdx+20h]
0x180009acf  cmp     ebp, [rsi+4]
0x180009ad2  jb      short loc_180009AA0
0x180009ad4  mov     ecx, [rdi+7Ch]
0x180009ad7  add     rcx, 28h ; '('
0x180009adb  add     rcx, rdi
0x180009ade  mov     [rsp+58h+arg_0], rcx
0x180009ae3  mov     [rcx], ebp
0x180009ae5  mov     rax, [rsp+58h+arg_0]
0x180009aea  mov     [rax+4], r14d
0x180009aee  jmp     short loc_180009B1D
0x180009af0  mov     r8d, 275h; int
0x180009af6  lea     r9, aErrorD; "Error = %d"
0x180009afd  mov     dword ptr [rsp+58h+Args], 6Fh ; 'o'; Args
0x180009b05  lea     rdx, aWdipwriteparam_1; "WdipWriteParameterCollectionToMessageBu"...
0x180009b0c  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009b13  call    WdipTraceError
0x180009b18  mov     ebx, 80070216h
0x180009b1d  mov     rbp, [rsp+58h+arg_10]
0x180009b22  mov     eax, ebx
0x180009b24  mov     rbx, [rsp+58h+arg_8]
0x180009b29  add     rsp, 30h
0x180009b2d  pop     r15
0x180009b2f  pop     r14
0x180009b31  pop     r12
0x180009b33  pop     rdi
0x180009b34  pop     rsi
0x180009b35  retn
```

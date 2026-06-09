# DpspVerifyTaskFolder(void)

- ea: `0x180016da4`
- end: `0x180016f6a`
- name: `?DpspVerifyTaskFolder@@YAJXZ`
- size: `454`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016bd4`

## callees

- `0x180009090`
- `0x180016da4`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016ec4`
- `OLEAUT32!__imp_SysAllocString` at `0x180016ec4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4d`
- `OLEAUT32!__imp_VariantInit` at `0x180016dd7`
- `OLEAUT32!__imp_VariantInit` at `0x180016dd7`
- `OLEAUT32!__imp_VariantClear` at `0x180016f3f`
- `OLEAUT32!__imp_VariantClear` at `0x180016f3f`

## string_xrefs

- `0x180016e5b`: `DpspVerifyTaskFolder`
- `0x180016e62`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`

## pseudocode

```c
__int64 DpspVerifyTaskFolder(void)
{
  unsigned int v0; // ebx
  OLECHAR *v1; // rdi
  __int64 v2; // rax
  __int64 (__fastcall *v3)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  int v4; // eax
  int v5; // r8d
  int v6; // eax
  BSTR v7; // rax
  int v8; // eax
  char Args[8]; // [rsp+20h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  __int128 v12; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-19h]
  VARIANTARG v14; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v15; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v16; // [rsp+B0h] [rbp+37h] BYREF
  unsigned int v17; // [rsp+E0h] [rbp+67h] BYREF
  signed __int64 v18; // [rsp+E8h] [rbp+6Fh] BYREF

  v0 = 0;
  v18 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v1 = 0;
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( !g_pTaskFolder )
  {
    v12 = *(_OWORD *)&pvarg.vt;
    v2 = *(_QWORD *)g_pTaskService;
    pRecInfo = pvarg.pRecInfo;
    v14 = pvarg;
    v3 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v2 + 80);
    v15 = pvarg;
    v16 = pvarg;
    v4 = v3(g_pTaskService, &v16, &v15, &v14, &v12);
    v0 = v4;
    if ( v4 < 0 )
    {
      v5 = 67;
      *(_DWORD *)Args = (unsigned __int16)v4;
LABEL_4:
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (__int64)L"DpspVerifyTaskFolder",
        v5,
        (const wchar_t *)L"Error = %d",
        *(_QWORD *)Args);
      goto LABEL_15;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)g_pTaskService + 120LL))(g_pTaskService, &v17);
    v0 = v6;
    if ( v6 < 0 )
    {
      v5 = 74;
      *(_DWORD *)Args = (unsigned __int16)v6;
      goto LABEL_4;
    }
    if ( v17 < 0x10002 )
    {
      v0 = -2147216619;
      *(_DWORD *)Args = 4885;
      v5 = 78;
      goto LABEL_4;
    }
    v7 = SysAllocString(L"\\Microsoft\\Windows\\WDI");
    v1 = v7;
    if ( !v7 )
    {
      v0 = -2147024882;
      *(_DWORD *)Args = 14;
      v5 = 82;
      goto LABEL_4;
    }
    v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, signed __int64 *))(*(_QWORD *)g_pTaskService + 56LL))(
           g_pTaskService,
           v7,
           &v18);
    v0 = v8;
    if ( v8 < 0 )
    {
      v5 = 87;
      *(_DWORD *)Args = (unsigned __int16)v8;
      goto LABEL_4;
    }
    if ( _InterlockedCompareExchange64(&g_pTaskFolder, v18, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
LABEL_15:
  VariantClear(&pvarg);
  if ( v1 )
    SysFreeString(v1);
  return v0;
}

```

## disassembly

```asm
0x180016da4  mov     [rsp-8+arg_10], rbx
0x180016da9  mov     [rsp-8+arg_18], rdi
0x180016dae  push    rbp
0x180016daf  lea     rbp, [rsp-57h]
0x180016db4  sub     rsp, 0D0h
0x180016dbb  xor     ebx, ebx
0x180016dbd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016dc1  xorps   xmm0, xmm0
0x180016dc4  mov     [rbp+57h+arg_8], rbx
0x180016dc8  xor     eax, eax
0x180016dca  mov     [rbp+57h+arg_0], ebx
0x180016dcd  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180016dd1  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180016dd5  xor     edi, edi
0x180016dd7  call    cs:__imp_VariantInit
0x180016ddd  cmp     cs:g_pTaskFolder, rbx
0x180016de4  mov     qword ptr [rbp+57h+pvarg+8], rbx
0x180016de8  jnz     loc_180016F3B
0x180016dee  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180016df2  lea     rdx, [rbp+57h+var_80]
0x180016df6  mov     rcx, cs:g_pTaskService
0x180016dfd  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180016e02  lea     r9, [rbp+57h+var_60]
0x180016e06  mov     qword ptr [rsp+0D0h+Args], rdx
0x180016e0b  lea     r8, [rbp+57h+var_40]
0x180016e0f  lea     rdx, [rbp+57h+var_20]
0x180016e13  movaps  [rbp+57h+var_80], xmm1
0x180016e17  mov     rax, [rcx]
0x180016e1a  movsd   [rbp+57h+var_70], xmm0
0x180016e1f  movaps  [rbp+57h+var_60], xmm1
0x180016e23  movsd   [rbp+57h+var_50], xmm0
0x180016e28  mov     rax, [rax+50h]
0x180016e2c  movaps  [rbp+57h+var_40], xmm1
0x180016e30  movsd   [rbp+57h+var_30], xmm0
0x180016e35  movaps  [rbp+57h+var_20], xmm1
0x180016e39  movsd   [rbp+57h+var_10], xmm0
0x180016e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e43  mov     ebx, eax
0x180016e45  test    eax, eax
0x180016e47  jns     short loc_180016E73
0x180016e49  movzx   ecx, ax
0x180016e4c  lea     r8d, [rdi+43h]; int
0x180016e50  mov     dword ptr [rsp+0D0h+Args], ecx; Args
0x180016e54  lea     r9, aErrorD; "Error = %d"
0x180016e5b  lea     rdx, aDpspverifytask_0; "DpspVerifyTaskFolder"
0x180016e62  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016e69  call    WdipTraceError
0x180016e6e  jmp     loc_180016F3B
0x180016e73  mov     rcx, cs:g_pTaskService
0x180016e7a  lea     rdx, [rbp+57h+arg_0]
0x180016e7e  mov     rax, [rcx]
0x180016e81  mov     rax, [rax+78h]
0x180016e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e8a  mov     ebx, eax
0x180016e8c  test    eax, eax
0x180016e8e  jns     short loc_180016E9F
0x180016e90  movzx   eax, ax
0x180016e93  mov     r8d, 4Ah ; 'J'
0x180016e99  mov     dword ptr [rsp+0D0h+Args], eax
0x180016e9d  jmp     short loc_180016E54
0x180016e9f  cmp     [rbp+57h+arg_0], 10002h
0x180016ea6  jnb     short loc_180016EBD
0x180016ea8  mov     ebx, 80041315h
0x180016ead  mov     dword ptr [rsp+0D0h+Args], 1315h
0x180016eb5  mov     r8d, 4Eh ; 'N'
0x180016ebb  jmp     short loc_180016E54
0x180016ebd  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\WDI"
0x180016ec4  call    cs:__imp_SysAllocString
0x180016eca  mov     rdi, rax
0x180016ecd  test    rax, rax
0x180016ed0  jnz     short loc_180016EE8
0x180016ed2  mov     ebx, 8007000Eh
0x180016ed7  mov     dword ptr [rsp+0D0h+Args], 0Eh
0x180016edf  lea     r8d, [rax+52h]
0x180016ee3  jmp     loc_180016E54
0x180016ee8  mov     rcx, cs:g_pTaskService
0x180016eef  lea     r8, [rbp+57h+arg_8]
0x180016ef3  mov     rdx, rdi
0x180016ef6  mov     rax, [rcx]
0x180016ef9  mov     rax, [rax+38h]
0x180016efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f02  mov     ebx, eax
0x180016f04  test    eax, eax
0x180016f06  jns     short loc_180016F1A
0x180016f08  movzx   eax, ax
0x180016f0b  mov     r8d, 57h ; 'W'
0x180016f11  mov     dword ptr [rsp+0D0h+Args], eax
0x180016f15  jmp     loc_180016E54
0x180016f1a  mov     rcx, [rbp+57h+arg_8]
0x180016f1e  xor     eax, eax
0x180016f20  lock cmpxchg cs:g_pTaskFolder, rcx
0x180016f29  jz      short loc_180016F3B
0x180016f2b  mov     rcx, [rbp+57h+arg_8]
0x180016f2f  mov     rax, [rcx]
0x180016f32  mov     rax, [rax+10h]
0x180016f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016f3f  call    cs:__imp_VariantClear
0x180016f45  test    rdi, rdi
0x180016f48  jz      short loc_180016F53
0x180016f4a  mov     rcx, rdi; bstrString
0x180016f4d  call    cs:__imp_SysFreeString
0x180016f53  lea     r11, [rsp+0D0h+var_s0]
0x180016f5b  mov     eax, ebx
0x180016f5d  mov     rbx, [r11+20h]
0x180016f61  mov     rdi, [r11+28h]
0x180016f65  mov     rsp, r11
0x180016f68  pop     rbp
0x180016f69  retn
```

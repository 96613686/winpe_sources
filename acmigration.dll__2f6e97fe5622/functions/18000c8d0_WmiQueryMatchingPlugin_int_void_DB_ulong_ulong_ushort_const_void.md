# WmiQueryMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18000c8d0`
- end: `0x18000c96b`
- name: `?WmiQueryMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `155`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c8d0`
- `0x18000c974`
- `0x1800543c0`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000c8e7`
- `ole32!CoInitializeEx` at `0x18000c8e7`
- `ole32!CoUninitialize` at `0x18000c955`
- `ole32!CoUninitialize` at `0x18000c955`

## string_xrefs

- `0x18000c8fb`: `0x%08x Failed to initialize COM`
- `0x18000c908`: `WmiQueryMatchingPlugin`
- `0x18000c93c`: `WmiQueryMatchingPlugin`

## pseudocode

```c
__int64 __fastcall WmiQueryMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  HRESULT v7; // eax
  int v8; // ebx

  *(_DWORD *)this = 0;
  v7 = CoInitializeEx(0, 0);
  v8 = v7;
  if ( v7 >= 0 )
    WmiQueryMatchingPluginHelper(this, a6, (unsigned __int16 *)a5);
  else
    AslLogCallPrintf(1, "WmiQueryMatchingPlugin", 465, "0x%08x Failed to initialize COM", v7);
  if ( v8 >= 0 )
    CoUninitialize();
  return 1;
}

```

## disassembly

```asm
0x18000c8d0  mov     [rsp+arg_8], rbx
0x18000c8d5  push    rdi
0x18000c8d6  sub     rsp, 30h
0x18000c8da  mov     rdi, rcx
0x18000c8dd  mov     dword ptr [rcx], 0
0x18000c8e3  xor     edx, edx; dwCoInit
0x18000c8e5  xor     ecx, ecx; pvReserved
0x18000c8e7  call    cs:__imp_CoInitializeEx
0x18000c8ed  mov     ebx, eax
0x18000c8ef  mov     [rsp+38h+arg_0], eax
0x18000c8f3  test    eax, eax
0x18000c8f5  jns     short loc_18000C91B
0x18000c8f7  mov     [rsp+38h+var_18], eax
0x18000c8fb  lea     r9, a0x08xFailedToI; "0x%08x Failed to initialize COM"
0x18000c902  mov     r8d, 1D1h
0x18000c908  lea     rdx, aWmiquerymatchi_0; "WmiQueryMatchingPlugin"
0x18000c90f  mov     ecx, 1
0x18000c914  call    AslLogCallPrintf
0x18000c919  jmp     short loc_18000C951
0x18000c91b  mov     r8d, dword ptr [rsp+38h+arg_20]; unsigned __int16 *
0x18000c920  mov     rdx, [rsp+38h+arg_28]; unsigned __int16 *
0x18000c925  mov     rcx, rdi; this
0x18000c928  call    ?WmiQueryMatchingPluginHelper@@YAXPEAHPEBGK@Z; WmiQueryMatchingPluginHelper(int *,ushort const *,ulong)
0x18000c92d  jmp     short loc_18000C951
0x18000c92f  lea     r9, aExceptionStack; "EXCEPTION_STACK_OVERFLOW"
0x18000c936  mov     r8d, 1DCh
0x18000c93c  lea     rdx, aWmiquerymatchi_0; "WmiQueryMatchingPlugin"
0x18000c943  mov     ecx, 1
0x18000c948  call    AslLogCallPrintf
0x18000c94d  mov     ebx, [rsp+38h+arg_0]
0x18000c951  test    ebx, ebx
0x18000c953  js      short loc_18000C95B
0x18000c955  call    cs:__imp_CoUninitialize
0x18000c95b  mov     eax, 1
0x18000c960  mov     rbx, [rsp+38h+arg_8]
0x18000c965  add     rsp, 30h
0x18000c969  pop     rdi
0x18000c96a  retn
0x180065ec4  push    rbp
0x180065ec6  sub     rsp, 30h
0x180065eca  mov     rbp, rdx
0x180065ecd  mov     rax, [rcx]
0x180065ed0  xor     ecx, ecx
0x180065ed2  cmp     dword ptr [rax], 0C00000FDh
0x180065ed8  setz    cl
0x180065edb  mov     eax, ecx
0x180065edd  add     rsp, 30h
0x180065ee1  pop     rbp
0x180065ee2  retn
```

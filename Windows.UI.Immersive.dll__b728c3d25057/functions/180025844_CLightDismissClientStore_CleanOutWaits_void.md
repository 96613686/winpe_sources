# CLightDismissClientStore::_CleanOutWaits(void)

- ea: `0x180025844`
- end: `0x18002599b`
- name: `?_CleanOutWaits@CLightDismissClientStore@@AEAAXXZ`
- size: `343`
- prototype: `void __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800256d0`
- `0x18007fb78`

## callees

- `0x180025844`
- `0x180046b90`
- `0x180056c12`
- `0x18007f738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180025904`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180025904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025968`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002595f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002595f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002597c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002597c`

## pseudocode

```c
void __fastcall CLightDismissClientStore::_CleanOutWaits(CLightDismissClientStore *this)
{
  _DWORD *v1; // rsi
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // r15
  __int64 j; // r14
  int v6; // eax
  _DWORD *v7; // rcx
  unsigned __int64 v8; // r14
  DWORD ProcessId; // eax
  unsigned __int64 k; // rcx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  void *v13; // r15
  void *v14; // r12
  _DWORD *v15; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h]
  __int64 v17; // [rsp+30h] [rbp-10h]
  __int64 i; // [rsp+38h] [rbp-8h]
  char v19; // [rsp+70h] [rbp+30h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  for ( i = 0; v3 < *((_QWORD *)this + 12); ++v3 )
  {
    for ( j = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v3); j; j = *(_QWORD *)(j + 56) )
    {
      if ( (int)CTSimpleFixedArray<unsigned long,CSimpleArrayStandardCompareHelper<unsigned long>>::Find(
                  &v15,
                  j + 20,
                  &v19) < 0 )
      {
        if ( v2 != i
          || (v6 = CTSimpleArray<unsigned long,4294967294,CTPolicyCoTaskMem<unsigned long>,CSimpleArrayStandardCompareHelper<unsigned long>,CSimpleArrayStandardMergeHelper<unsigned long>>::_EnsureCapacity(
                     &v15,
                     v2 + 1),
              v2 = v16,
              v1 = v15,
              v6 >= 0) )
        {
          v16 = ++v2;
          v7 = &v1[v2 - 1];
          if ( v7 )
            *v7 = *(_DWORD *)(j + 20);
        }
      }
    }
  }
  v8 = 0;
  while ( v8 < *((_QWORD *)this + 8) )
  {
    ProcessId = GetProcessId(*(HANDLE *)(*((_QWORD *)this + 7) + 16 * v8 + 8));
    for ( k = 0; k < v2; ++k )
    {
      if ( v1[k] == ProcessId )
      {
        ++v8;
        goto LABEL_22;
      }
    }
    v11 = *((_QWORD *)this + 8);
    v12 = 16 * v8 + *((_QWORD *)this + 7);
    v13 = *(void **)v12;
    v14 = *(void **)(v12 + 8);
    if ( v8 < v11 )
    {
      if ( v8 != v11 - 1 )
        memmove_0((void *)v12, (const void *)(v12 + 16), 16 * (v11 - v8) - 16);
      --*((_QWORD *)this + 8);
    }
    UnregisterWaitEx(v13, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CloseHandle(v14);
LABEL_22:
    ;
  }
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180025844  mov     [rsp-28h+arg_8], rbx
0x180025849  mov     [rsp-28h+arg_10], rsi
0x18002584e  push    rbp
0x18002584f  push    rdi
0x180025850  push    r12
0x180025852  push    r14
0x180025854  push    r15
0x180025856  mov     rbp, rsp
0x180025859  sub     rsp, 40h
0x18002585d  xor     esi, esi
0x18002585f  xor     edi, edi
0x180025861  xor     r15d, r15d
0x180025864  mov     [rbp+var_20], rsi
0x180025868  mov     rbx, rcx
0x18002586b  mov     [rbp+var_18], rdi
0x18002586f  mov     [rbp+var_10], rsi
0x180025873  mov     [rbp+var_8], rsi
0x180025877  cmp     [rcx+60h], rsi
0x18002587b  jbe     short loc_1800258E7
0x18002587d  mov     rax, [rbx+58h]
0x180025881  mov     r14, [rax+r15*8]
0x180025885  jmp     short loc_1800258D9
0x180025887  lea     r8, [rbp+arg_0]
0x18002588b  lea     rdx, [r14+14h]
0x18002588f  lea     rcx, [rbp+var_20]
0x180025893  call    ?Find@?$CTSimpleFixedArray@KV?$CSimpleArrayStandardCompareHelper@K@@@@QEBAJAEBKPEA_K_K@Z; CTSimpleFixedArray<ulong,CSimpleArrayStandardCompareHelper<ulong>>::Find(ulong const &,unsigned __int64 *,unsigned __int64)
0x180025898  test    eax, eax
0x18002589a  jns     short loc_1800258D5
0x18002589c  cmp     rdi, [rbp+var_8]
0x1800258a0  jnz     short loc_1800258BB
0x1800258a2  lea     rdx, [rdi+1]
0x1800258a6  lea     rcx, [rbp+var_20]
0x1800258aa  call    ?_EnsureCapacity@?$CTSimpleArray@K$0PPPPPPPO@V?$CTPolicyCoTaskMem@K@@V?$CSimpleArrayStandardCompareHelper@K@@V?$CSimpleArrayStandardMergeHelper@K@@@@QEAAJ_K0@Z; CTSimpleArray<ulong,4294967294,CTPolicyCoTaskMem<ulong>,CSimpleArrayStandardCompareHelper<ulong>,CSimpleArrayStandardMergeHelper<ulong>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800258af  mov     rdi, [rbp+var_18]
0x1800258b3  mov     rsi, [rbp+var_20]
0x1800258b7  test    eax, eax
0x1800258b9  js      short loc_1800258D5
0x1800258bb  inc     rdi
0x1800258be  mov     [rbp+var_18], rdi
0x1800258c2  lea     rcx, [rdi-1]
0x1800258c6  lea     rcx, [rsi+rcx*4]
0x1800258ca  test    rcx, rcx
0x1800258cd  jz      short loc_1800258D5
0x1800258cf  mov     eax, [r14+14h]
0x1800258d3  mov     [rcx], eax
0x1800258d5  mov     r14, [r14+38h]
0x1800258d9  test    r14, r14
0x1800258dc  jnz     short loc_180025887
0x1800258de  inc     r15
0x1800258e1  cmp     r15, [rbx+60h]
0x1800258e5  jb      short loc_18002587D
0x1800258e7  xor     r14d, r14d
0x1800258ea  cmp     [rbx+40h], r14
0x1800258ee  jbe     loc_180025974
0x1800258f4  mov     rcx, [rbx+38h]
0x1800258f8  mov     r15, r14
0x1800258fb  shl     r15, 4
0x1800258ff  mov     rcx, [rcx+r15+8]; Process
0x180025904  call    cs:__imp_GetProcessId
0x18002590a  xor     ecx, ecx
0x18002590c  cmp     rcx, rdi
0x18002590f  jnb     short loc_180025920
0x180025911  cmp     [rsi+rcx*4], eax
0x180025914  jz      short loc_18002591B
0x180025916  inc     rcx
0x180025919  jmp     short loc_18002590C
0x18002591b  inc     r14
0x18002591e  jmp     short loc_18002596E
0x180025920  mov     rcx, [rbx+38h]
0x180025924  mov     r8, [rbx+40h]
0x180025928  add     rcx, r15; void *
0x18002592b  mov     r15, [rcx]
0x18002592e  mov     r12, [rcx+8]
0x180025932  cmp     r14, r8
0x180025935  jnb     short loc_180025958
0x180025937  lea     rax, [r8-1]
0x18002593b  cmp     r14, rax
0x18002593e  jz      short loc_180025954
0x180025940  sub     r8, r14
0x180025943  lea     rdx, [rcx+10h]; Src
0x180025947  shl     r8, 4
0x18002594b  sub     r8, 10h; Size
0x18002594f  call    memmove_0
0x180025954  dec     qword ptr [rbx+40h]
0x180025958  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002595c  mov     rcx, r15; WaitHandle
0x18002595f  call    cs:__imp_UnregisterWaitEx
0x180025965  mov     rcx, r12; hObject
0x180025968  call    cs:__imp_CloseHandle
0x18002596e  cmp     r14, [rbx+40h]
0x180025972  jb      short loc_1800258F4
0x180025974  test    rsi, rsi
0x180025977  jz      short loc_180025982
0x180025979  mov     rcx, rsi; pv
0x18002597c  call    cs:__imp_CoTaskMemFree
0x180025982  lea     r11, [rsp+40h+var_s0]
0x180025987  mov     rbx, [r11+38h]
0x18002598b  mov     rsi, [r11+40h]
0x18002598f  mov     rsp, r11
0x180025992  pop     r15
0x180025994  pop     r14
0x180025996  pop     r12
0x180025998  pop     rdi
0x180025999  pop     rbp
0x18002599a  retn
```

# DisableValidationTask(void)

- ea: `0x180002e74`
- end: `0x180002fc8`
- name: `?DisableValidationTask@@YAJXZ`
- size: `340`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003ac0`

## callees

- `0x180002e74`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002ec7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002ec7`

## pseudocode

```c
__int64 DisableValidationTask(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rax
  __int64 (__fastcall *v2)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  __int128 v4; // [rsp+30h] [rbp-39h] BYREF
  __int64 v5; // [rsp+40h] [rbp-29h]
  __int128 v6; // [rsp+50h] [rbp-19h] BYREF
  __int64 v7; // [rsp+60h] [rbp-9h]
  __int128 v8; // [rsp+70h] [rbp+7h] BYREF
  __int64 v9; // [rsp+80h] [rbp+17h]
  __int128 v10; // [rsp+90h] [rbp+27h] BYREF
  __int64 v11; // [rsp+A0h] [rbp+37h]
  LPVOID ppv; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v13; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v14; // [rsp+E0h] [rbp+77h] BYREF

  ppv = 0;
  v14 = 0;
  v4 = 0;
  v13 = 0;
  LOWORD(v4) = 1;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( !v0 )
  {
    v5 = 0;
    v1 = *(_QWORD *)ppv;
    v6 = v4;
    v7 = 0;
    v8 = v4;
    v2 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(v1 + 80);
    v9 = 0;
    v10 = v4;
    v11 = 0;
    v0 = v2(ppv, &v10, &v8, &v6, &v4);
    if ( !v0 )
    {
      v0 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, L"\\", &v14);
      if ( !v0 )
      {
        v0 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v14 + 104LL))(
               v14,
               L"Microsoft\\Windows\\WOF\\WIM-Hash-Validation",
               &v13);
        if ( !v0 )
          v0 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 88LL))(v13, 0);
      }
    }
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x180002e74  push    rbp
0x180002e76  push    rbx
0x180002e77  push    rsi
0x180002e78  lea     rbp, [rsp-47h]
0x180002e7d  sub     rsp, 0B0h
0x180002e84  xorps   xmm0, xmm0
0x180002e87  mov     [rbp+57h+arg_0], 0
0x180002e8f  lea     rax, [rbp+57h+arg_0]
0x180002e93  mov     [rbp+57h+arg_10], 0
0x180002e9b  movups  [rbp+57h+var_90], xmm0
0x180002e9f  xor     esi, esi
0x180002ea1  mov     [rbp+57h+arg_8], 0
0x180002ea9  lea     r9, IID_ITaskService; riid
0x180002eb0  mov     [rsp+0C0h+ppv], rax; ppv
0x180002eb5  xor     edx, edx; pUnkOuter
0x180002eb7  lea     rcx, CLSID_TaskScheduler; rclsid
0x180002ebe  lea     r8d, [rsi+1]; dwClsContext
0x180002ec2  mov     word ptr [rbp+57h+var_90], r8w
0x180002ec7  call    cs:__imp_CoCreateInstance
0x180002ecd  mov     ebx, eax
0x180002ecf  test    eax, eax
0x180002ed1  jnz     loc_180002F7C
0x180002ed7  movups  xmm1, [rbp+57h+var_90]
0x180002edb  mov     rcx, [rbp+57h+arg_0]
0x180002edf  lea     rdx, [rbp+57h+var_90]
0x180002ee3  mov     [rsp+0C0h+ppv], rdx
0x180002ee8  lea     r9, [rbp+57h+var_70]
0x180002eec  lea     r8, [rbp+57h+var_50]
0x180002ef0  movaps  [rbp+57h+var_90], xmm1
0x180002ef4  lea     rdx, [rbp+57h+var_30]
0x180002ef8  mov     [rbp+57h+var_80], rsi
0x180002efc  mov     rax, [rcx]
0x180002eff  movaps  [rbp+57h+var_70], xmm1
0x180002f03  mov     [rbp+57h+var_60], rsi
0x180002f07  movaps  [rbp+57h+var_50], xmm1
0x180002f0b  mov     rax, [rax+50h]
0x180002f0f  mov     [rbp+57h+var_40], rsi
0x180002f13  movaps  [rbp+57h+var_30], xmm1
0x180002f17  mov     [rbp+57h+var_20], rsi
0x180002f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f20  mov     ebx, eax
0x180002f22  test    eax, eax
0x180002f24  jnz     short loc_180002F7C
0x180002f26  mov     rcx, [rbp+57h+arg_0]
0x180002f2a  lea     r8, [rbp+57h+arg_10]
0x180002f2e  lea     rdx, asc_180007650; "\\"
0x180002f35  mov     rax, [rcx]
0x180002f38  mov     rax, [rax+38h]
0x180002f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f41  mov     ebx, eax
0x180002f43  test    eax, eax
0x180002f45  jnz     short loc_180002F7C
0x180002f47  mov     rcx, [rbp+57h+arg_10]
0x180002f4b  lea     r8, [rbp+57h+arg_8]
0x180002f4f  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\WOF\\WIM-Hash-Valid"...
0x180002f56  mov     rax, [rcx]
0x180002f59  mov     rax, [rax+68h]
0x180002f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f62  mov     ebx, eax
0x180002f64  test    eax, eax
0x180002f66  jnz     short loc_180002F7C
0x180002f68  mov     rcx, [rbp+57h+arg_8]
0x180002f6c  xor     edx, edx
0x180002f6e  mov     rax, [rcx]
0x180002f71  mov     rax, [rax+58h]
0x180002f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7a  mov     ebx, eax
0x180002f7c  mov     rcx, [rbp+57h+arg_8]
0x180002f80  test    rcx, rcx
0x180002f83  jz      short loc_180002F91
0x180002f85  mov     rax, [rcx]
0x180002f88  mov     rax, [rax+10h]
0x180002f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f91  mov     rcx, [rbp+57h+arg_10]
0x180002f95  test    rcx, rcx
0x180002f98  jz      short loc_180002FA6
0x180002f9a  mov     rax, [rcx]
0x180002f9d  mov     rax, [rax+10h]
0x180002fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa6  mov     rcx, [rbp+57h+arg_0]
0x180002faa  test    rcx, rcx
0x180002fad  jz      short loc_180002FBB
0x180002faf  mov     rax, [rcx]
0x180002fb2  mov     rax, [rax+10h]
0x180002fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbb  mov     eax, ebx
0x180002fbd  add     rsp, 0B0h
0x180002fc4  pop     rsi
0x180002fc5  pop     rbx
0x180002fc6  pop     rbp
0x180002fc7  retn
```

# CRegistryChangeListener::Shutdown(void)

- ea: `0x180009370`
- end: `0x1800093ac`
- name: `?Shutdown@CRegistryChangeListener@@UEAAJXZ`
- size: `60`
- prototype: `__int64 __fastcall(CRegistryChangeListener *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009180`

## callees

- `0x180009370`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009387`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009387`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000939e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000939e`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::Shutdown(CRegistryChangeListener *this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_WORK *v3; // rcx

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v2 )
    SetThreadpoolWait(v2, 0, 0);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    SubmitThreadpoolWork(v3);
  return 0;
}

```

## disassembly

```asm
0x180009370  push    rbx
0x180009372  sub     rsp, 20h
0x180009376  mov     rbx, rcx
0x180009379  mov     rcx, [rcx+20h]; pwa
0x18000937d  test    rcx, rcx
0x180009380  jz      short loc_18000938D
0x180009382  xor     r8d, r8d; pftTimeout
0x180009385  xor     edx, edx; h
0x180009387  call    cs:__imp_SetThreadpoolWait
0x18000938d  mov     rcx, [rbx+38h]; pwk
0x180009391  mov     qword ptr [rbx+30h], 0
0x180009399  test    rcx, rcx
0x18000939c  jz      short loc_1800093A4
0x18000939e  call    cs:__imp_SubmitThreadpoolWork
0x1800093a4  xor     eax, eax
0x1800093a6  add     rsp, 20h
0x1800093aa  pop     rbx
0x1800093ab  retn
```

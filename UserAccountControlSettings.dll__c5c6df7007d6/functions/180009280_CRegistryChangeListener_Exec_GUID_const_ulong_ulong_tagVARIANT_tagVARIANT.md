# CRegistryChangeListener::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x180009280`
- end: `0x1800092e9`
- name: `?Exec@CRegistryChangeListener@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `105`
- prototype: `__int64 __fastcall(CRegistryChangeListener *this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180009280`
- `0x180009618`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800092c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800092c7`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::Exec(CRegistryChangeListener *this, const struct _GUID *a2, int a3)
{
  __int64 result; // rax
  __int64 v5; // rax

  result = 0;
  if ( *((_QWORD *)this + 7) )
  {
    if ( !a2 )
      return 2147746048LL;
    v5 = 0x4B2FFA9E23F53115LL - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&a2->Data1 == 0x4B2FFA9E23F53115LL )
      v5 = 0x971D0D7C43B93180uLL - *(_QWORD *)a2->Data4;
    if ( v5 || a3 )
    {
      return 2147746048LL;
    }
    else
    {
      CRegistryChangeListener::_RestoreChangeCallback(this);
      SetThreadpoolWait(*((PTP_WAIT *)this + 5), *((HANDLE *)this + 3), 0);
      (*((void (__fastcall **)(_QWORD))this + 7))(*((_QWORD *)this + 9));
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009280  push    rbx
0x180009282  sub     rsp, 20h
0x180009286  xor     eax, eax
0x180009288  mov     rbx, rcx
0x18000928b  cmp     [rcx+38h], rax
0x18000928f  jz      short loc_1800092E3
0x180009291  test    rdx, rdx
0x180009294  jz      short loc_1800092DE
0x180009296  mov     rax, cs:qword_18000F428
0x18000929d  sub     rax, [rdx]
0x1800092a0  jnz     short loc_1800092AD
0x1800092a2  mov     rax, cs:qword_18000F430
0x1800092a9  sub     rax, [rdx+8]
0x1800092ad  test    rax, rax
0x1800092b0  jnz     short loc_1800092DE
0x1800092b2  test    r8d, r8d
0x1800092b5  jnz     short loc_1800092DE
0x1800092b7  call    ?_RestoreChangeCallback@CRegistryChangeListener@@AEAAJXZ; CRegistryChangeListener::_RestoreChangeCallback(void)
0x1800092bc  mov     rdx, [rbx+18h]; h
0x1800092c0  xor     r8d, r8d; pftTimeout
0x1800092c3  mov     rcx, [rbx+28h]; pwa
0x1800092c7  call    cs:__imp_SetThreadpoolWait
0x1800092cd  mov     rcx, [rbx+48h]
0x1800092d1  mov     rax, [rbx+38h]
0x1800092d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092da  xor     eax, eax
0x1800092dc  jmp     short loc_1800092E3
0x1800092de  mov     eax, 80040100h
0x1800092e3  add     rsp, 20h
0x1800092e7  pop     rbx
0x1800092e8  retn
```

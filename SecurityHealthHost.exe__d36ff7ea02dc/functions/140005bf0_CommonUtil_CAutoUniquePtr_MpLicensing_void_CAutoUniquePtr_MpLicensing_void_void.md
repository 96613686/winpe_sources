# CommonUtil::CAutoUniquePtr<MpLicensing,void>::~CAutoUniquePtr<MpLicensing,void>(void)

- ea: `0x140005bf0`
- end: `0x140005c3e`
- name: `??1?$CAutoUniquePtr@VMpLicensing@@X@CommonUtil@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fc89`

## callees

- `0x140001614`
- `0x140005bf0`
- `0x14000d000`
- `0x140011010`

## pseudocode

```c
void __fastcall CommonUtil::CAutoUniquePtr<MpLicensing,void>::~CAutoUniquePtr<MpLicensing,void>(void **a1)
{
  void *v1; // rbx
  __int64 v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    _HMODULE_Finalizer((HINSTANCE)_InterlockedExchange64((volatile __int64 *)v1 + 1, 0), *((void **)v1 + 2));
    if ( *(_QWORD *)v1 )
    {
      v2 = *(int *)(**(_QWORD **)v1 + 4LL) + *(_QWORD *)v1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    }
    operator delete(v1, 0x18u);
  }
}

```

## disassembly

```asm
0x140005bf0  push    rbx
0x140005bf2  sub     rsp, 20h
0x140005bf6  mov     rbx, [rcx]
0x140005bf9  test    rbx, rbx
0x140005bfc  jz      short loc_140005C38
0x140005bfe  xor     ecx, ecx
0x140005c00  xchg    rcx, [rbx+8]; HINSTANCE
0x140005c04  mov     rdx, [rbx+10h]; void *
0x140005c08  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x140005c0d  mov     rcx, [rbx]
0x140005c10  test    rcx, rcx
0x140005c13  jz      short loc_140005C2B
0x140005c15  mov     rax, [rcx]
0x140005c18  movsxd  rdx, dword ptr [rax+4]
0x140005c1c  add     rcx, rdx
0x140005c1f  mov     rax, [rcx]
0x140005c22  mov     rax, [rax+8]
0x140005c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c2b  mov     edx, 18h; unsigned __int64
0x140005c30  mov     rcx, rbx; void *
0x140005c33  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005c38  add     rsp, 20h
0x140005c3c  pop     rbx
0x140005c3d  retn
```

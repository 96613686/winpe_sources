# CommonUtil::CAutoUniquePtr<MpLicensing,void>::~CAutoUniquePtr<MpLicensing,void>(void)

- ea: `0x140007448`
- end: `0x140007496`
- name: `??1?$CAutoUniquePtr@VMpLicensing@@X@CommonUtil@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012366`

## callees

- `0x1400015f4`
- `0x140007448`
- `0x14000dd0c`
- `0x140013010`

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
0x140007448  push    rbx
0x14000744a  sub     rsp, 20h
0x14000744e  mov     rbx, [rcx]
0x140007451  test    rbx, rbx
0x140007454  jz      short loc_140007490
0x140007456  xor     ecx, ecx
0x140007458  xchg    rcx, [rbx+8]; HINSTANCE
0x14000745c  mov     rdx, [rbx+10h]; void *
0x140007460  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x140007465  mov     rcx, [rbx]
0x140007468  test    rcx, rcx
0x14000746b  jz      short loc_140007483
0x14000746d  mov     rax, [rcx]
0x140007470  movsxd  rdx, dword ptr [rax+4]
0x140007474  add     rcx, rdx
0x140007477  mov     rax, [rcx]
0x14000747a  mov     rax, [rax+8]
0x14000747e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007483  mov     edx, 18h; unsigned __int64
0x140007488  mov     rcx, rbx; void *
0x14000748b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007490  add     rsp, 20h
0x140007494  pop     rbx
0x140007495  retn
```

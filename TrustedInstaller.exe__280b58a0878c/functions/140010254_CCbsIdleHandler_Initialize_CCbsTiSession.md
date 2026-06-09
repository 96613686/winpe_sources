# CCbsIdleHandler::Initialize(CCbsTiSession *)

- ea: `0x140010254`
- end: `0x1400102b0`
- name: `?Initialize@CCbsIdleHandler@@QEAAJPEAVCCbsTiSession@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(CCbsIdleHandler *__hidden this, struct CCbsTiSession *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14000f990`

## callees

- `0x14002b010`

## string_xrefs

- `0x140010278`: `ScavengeTask`

## pseudocode

```c
__int64 __fastcall CCbsIdleHandler::Initialize(CCbsIdleHandler *this, struct CCbsTiSession *a2)
{
  CCbsIdleHandler *v2; // rbx
  __int64 v3; // rcx

  v2 = CCbsTiSession::m_pIdleScavengeHandler;
  *((_QWORD *)CCbsTiSession::m_pIdleScavengeHandler + 4) = a2;
  (*(void (__fastcall **)(struct CCbsTiSession *))(*(_QWORD *)a2 + 8LL))(a2);
  v3 = *((_QWORD *)v2 + 4) + *(int *)(*(_QWORD *)(*((_QWORD *)v2 + 4) + 16LL) + 4LL) + 16LL;
  (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v3 + 24LL))(
    v3,
    0,
    L"ScavengeTask",
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x140010254  push    rbx
0x140010256  sub     rsp, 30h
0x14001025a  mov     rbx, cs:?m_pIdleScavengeHandler@CCbsTiSession@@2PEAVCCbsIdleHandler@@EA; CCbsIdleHandler * CCbsTiSession::m_pIdleScavengeHandler
0x140010261  mov     rcx, rdx
0x140010264  mov     [rbx+20h], rdx
0x140010268  mov     rax, [rdx]
0x14001026b  mov     rax, [rax+8]
0x14001026f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010274  mov     rdx, [rbx+20h]
0x140010278  lea     r8, aScavengetask; "ScavengeTask"
0x14001027f  xor     r9d, r9d
0x140010282  mov     [rsp+38h+var_18], 0
0x14001028b  mov     rax, [rdx+10h]
0x14001028f  movsxd  rcx, dword ptr [rax+4]
0x140010293  add     rcx, 10h
0x140010297  add     rcx, rdx
0x14001029a  xor     edx, edx
0x14001029c  mov     rax, [rcx]
0x14001029f  mov     rax, [rax+18h]
0x1400102a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102a8  xor     eax, eax
0x1400102aa  add     rsp, 30h
0x1400102ae  pop     rbx
0x1400102af  retn
```

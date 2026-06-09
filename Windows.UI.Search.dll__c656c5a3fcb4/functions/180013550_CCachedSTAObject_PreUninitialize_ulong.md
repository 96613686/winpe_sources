# CCachedSTAObject::PreUninitialize(ulong)

- ea: `0x180013550`
- end: `0x1800135a9`
- name: `?PreUninitialize@CCachedSTAObject@@UEAAJK@Z`
- size: `89`
- prototype: `__int64 __fastcall(CCachedSTAObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013550`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001359b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001359b`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180013569`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180013569`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x180013573`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x180013573`

## pseudocode

```c
__int64 __fastcall CCachedSTAObject::PreUninitialize(ULARGE_INTEGER *this, int a2)
{
  ULARGE_INTEGER v3; // rcx

  if ( a2 == 1 )
  {
    this[5].LowPart = 0;
    CoRevokeInitializeSpy(this[2]);
    ((void (__fastcall *)(_QWORD))IUnknown_RemoveBackReferences)((ULARGE_INTEGER)this[4].QuadPart);
    v3 = this[4];
    if ( v3.QuadPart )
    {
      (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v3.QuadPart + 16LL))(v3);
      this[4].QuadPart = 0;
    }
    TlsSetValue(this[3].LowPart, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180013550  push    rbx
0x180013552  sub     rsp, 20h
0x180013556  mov     rbx, rcx
0x180013559  cmp     edx, 1
0x18001355c  jnz     short loc_1800135A1
0x18001355e  mov     dword ptr [rcx+28h], 0
0x180013565  mov     rcx, [rcx+10h]; uliCookie
0x180013569  call    cs:__imp_CoRevokeInitializeSpy
0x18001356f  mov     rcx, [rbx+20h]
0x180013573  call    cs:__imp_IUnknown_RemoveBackReferences
0x180013579  mov     rcx, [rbx+20h]
0x18001357d  test    rcx, rcx
0x180013580  jz      short loc_180013596
0x180013582  mov     rax, [rcx]
0x180013585  mov     rax, [rax+10h]
0x180013589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001358e  mov     qword ptr [rbx+20h], 0
0x180013596  mov     ecx, [rbx+18h]; dwTlsIndex
0x180013599  xor     edx, edx; lpTlsValue
0x18001359b  call    cs:__imp_TlsSetValue
0x1800135a1  xor     eax, eax
0x1800135a3  add     rsp, 20h
0x1800135a7  pop     rbx
0x1800135a8  retn
```

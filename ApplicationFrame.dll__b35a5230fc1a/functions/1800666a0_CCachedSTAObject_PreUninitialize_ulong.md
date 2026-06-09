# CCachedSTAObject::PreUninitialize(ulong)

- ea: `0x1800666a0`
- end: `0x1800666f9`
- name: `?PreUninitialize@CCachedSTAObject@@UEAAJK@Z`
- size: `89`
- prototype: `__int64 __fastcall(CCachedSTAObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800666a0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800666eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800666eb`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x1800666b9`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x1800666b9`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x1800666c3`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x1800666c3`

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
0x1800666a0  push    rbx
0x1800666a2  sub     rsp, 20h
0x1800666a6  mov     rbx, rcx
0x1800666a9  cmp     edx, 1
0x1800666ac  jnz     short loc_1800666F1
0x1800666ae  mov     dword ptr [rcx+28h], 0
0x1800666b5  mov     rcx, [rcx+10h]; uliCookie
0x1800666b9  call    cs:__imp_CoRevokeInitializeSpy
0x1800666bf  mov     rcx, [rbx+20h]
0x1800666c3  call    cs:__imp_IUnknown_RemoveBackReferences
0x1800666c9  mov     rcx, [rbx+20h]
0x1800666cd  test    rcx, rcx
0x1800666d0  jz      short loc_1800666E6
0x1800666d2  mov     rax, [rcx]
0x1800666d5  mov     rax, [rax+10h]
0x1800666d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666de  mov     qword ptr [rbx+20h], 0
0x1800666e6  mov     ecx, [rbx+18h]; dwTlsIndex
0x1800666e9  xor     edx, edx; lpTlsValue
0x1800666eb  call    cs:__imp_TlsSetValue
0x1800666f1  xor     eax, eax
0x1800666f3  add     rsp, 20h
0x1800666f7  pop     rbx
0x1800666f8  retn
```

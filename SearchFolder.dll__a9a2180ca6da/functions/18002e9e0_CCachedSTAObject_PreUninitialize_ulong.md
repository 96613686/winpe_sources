# CCachedSTAObject::PreUninitialize(ulong)

- ea: `0x18002e9e0`
- end: `0x18002ea39`
- name: `?PreUninitialize@CCachedSTAObject@@UEAAJK@Z`
- size: `89`
- prototype: `__int64 __fastcall(CCachedSTAObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002e9e0`
- `0x180051010`

## import_xrefs

- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x18002ea03`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x18002ea03`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ea2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ea2b`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x18002e9f9`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x18002e9f9`

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
0x18002e9e0  push    rbx
0x18002e9e2  sub     rsp, 20h
0x18002e9e6  mov     rbx, rcx
0x18002e9e9  cmp     edx, 1
0x18002e9ec  jnz     short loc_18002EA31
0x18002e9ee  mov     dword ptr [rcx+28h], 0
0x18002e9f5  mov     rcx, [rcx+10h]; uliCookie
0x18002e9f9  call    cs:__imp_CoRevokeInitializeSpy
0x18002e9ff  mov     rcx, [rbx+20h]
0x18002ea03  call    cs:__imp_IUnknown_RemoveBackReferences
0x18002ea09  mov     rcx, [rbx+20h]
0x18002ea0d  test    rcx, rcx
0x18002ea10  jz      short loc_18002EA26
0x18002ea12  mov     rax, [rcx]
0x18002ea15  mov     rax, [rax+10h]
0x18002ea19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea1e  mov     qword ptr [rbx+20h], 0
0x18002ea26  mov     ecx, [rbx+18h]; dwTlsIndex
0x18002ea29  xor     edx, edx; lpTlsValue
0x18002ea2b  call    cs:__imp_TlsSetValue
0x18002ea31  xor     eax, eax
0x18002ea33  add     rsp, 20h
0x18002ea37  pop     rbx
0x18002ea38  retn
```

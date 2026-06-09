# CCachedSTAObject::PreUninitialize(ulong)

- ea: `0x18004e760`
- end: `0x18004e7bb`
- name: `?PreUninitialize@CCachedSTAObject@@UEAAJK@Z`
- size: `91`
- prototype: `__int64 __fastcall(CCachedSTAObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18004e760`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004e7b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004e7b3`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x18004e781`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x18004e781`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x18004e78b`
- `SHCORE!__imp_IUnknown_RemoveBackReferences` at `0x18004e78b`

## pseudocode

```c
__int64 __fastcall CCachedSTAObject::PreUninitialize(ULARGE_INTEGER *this, int a2)
{
  ULARGE_INTEGER v4; // rcx

  if ( a2 == 1 )
  {
    this[5].LowPart = 0;
    CoRevokeInitializeSpy(this[2]);
    ((void (__fastcall *)(_QWORD))IUnknown_RemoveBackReferences)((ULARGE_INTEGER)this[4].QuadPart);
    v4 = this[4];
    if ( v4.QuadPart )
    {
      (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v4.QuadPart + 16LL))(v4);
      this[4].QuadPart = 0;
    }
    TlsSetValue(this[3].LowPart, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18004e760  push    rbx
0x18004e762  sub     rsp, 20h
0x18004e766  mov     rbx, rcx
0x18004e769  cmp     edx, 1
0x18004e76c  jz      short loc_18004E776
0x18004e76e  xor     eax, eax
0x18004e770  add     rsp, 20h
0x18004e774  pop     rbx
0x18004e775  retn
0x18004e776  mov     dword ptr [rcx+28h], 0
0x18004e77d  mov     rcx, [rcx+10h]; uliCookie
0x18004e781  call    cs:__imp_CoRevokeInitializeSpy
0x18004e787  mov     rcx, [rbx+20h]
0x18004e78b  call    cs:__imp_IUnknown_RemoveBackReferences
0x18004e791  mov     rcx, [rbx+20h]
0x18004e795  test    rcx, rcx
0x18004e798  jz      short loc_18004E7AE
0x18004e79a  mov     rax, [rcx]
0x18004e79d  mov     rax, [rax+10h]
0x18004e7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7a6  mov     qword ptr [rbx+20h], 0
0x18004e7ae  mov     ecx, [rbx+18h]; dwTlsIndex
0x18004e7b1  xor     edx, edx; lpTlsValue
0x18004e7b3  call    cs:__imp_TlsSetValue
0x18004e7b9  jmp     short loc_18004E76E
```

# CMetadataXMPReaderWriter::Release(void)

- ea: `0x18000fac0`
- end: `0x18000faf7`
- name: `?Release@CMetadataXMPReaderWriter@@UEAAKXZ`
- size: `55`
- prototype: `unsigned int __fastcall(CMetadataXMPReaderWriter *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180022d70`
- `0x180022d80`
- `0x180022d90`

## callees

- `0x18000fac0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::Release(CMetadataXMPReaderWriter *this)
{
  volatile signed __int32 *v1; // rcx
  unsigned __int32 v2; // ebx
  __int64 v4; // rax

  v1 = (volatile signed __int32 *)((char *)this + 24);
  v2 = _InterlockedDecrement(v1 + 2);
  if ( !v2 )
  {
    v4 = *(_QWORD *)v1;
    --*((_DWORD *)v1 + 2);
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(v4 + 24))(v1, 1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000fac0  push    rbx
0x18000fac2  sub     rsp, 20h
0x18000fac6  add     rcx, 18h
0x18000faca  mov     ebx, 0FFFFFFFFh
0x18000facf  lock xadd [rcx+8], ebx
0x18000fad4  sub     ebx, 1
0x18000fad7  jz      short loc_18000FAE1
0x18000fad9  mov     eax, ebx
0x18000fadb  add     rsp, 20h
0x18000fadf  pop     rbx
0x18000fae0  retn
0x18000fae1  mov     rax, [rcx]
0x18000fae4  mov     edx, 1
0x18000fae9  dec     dword ptr [rcx+8]
0x18000faec  mov     rax, [rax+18h]
0x18000faf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf5  jmp     short loc_18000FAD9
```

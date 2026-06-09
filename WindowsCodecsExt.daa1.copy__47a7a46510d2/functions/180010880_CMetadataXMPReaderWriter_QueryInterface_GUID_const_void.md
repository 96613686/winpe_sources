# CMetadataXMPReaderWriter::QueryInterface(_GUID const &,void * *)

- ea: `0x180010880`
- end: `0x1800108f5`
- name: `?QueryInterface@CMetadataXMPReaderWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180022d30`
- `0x180022d40`
- `0x180022d50`

## callees

- `0x180010880`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::QueryInterface(
        CMetadataXMPReaderWriter *this,
        const struct _GUID *a2,
        char **a3)
{
  int v4; // edi
  char *v5; // rcx
  __int64 v6; // rax

  v4 = -2147024809;
  if ( a3 )
  {
    v5 = (char *)this + 24;
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v6 )
    {
      v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 32LL))(v5);
      if ( v4 < 0 )
      {
        *a3 = 0;
        return (unsigned int)v4;
      }
    }
    else
    {
      *a3 = v5;
      v4 = 0;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)*a3 + 8LL))(*a3);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010880  mov     [rsp+arg_0], rbx
0x180010885  push    rdi
0x180010886  sub     rsp, 20h
0x18001088a  mov     rbx, r8
0x18001088d  mov     edi, 80070057h
0x180010892  test    r8, r8
0x180010895  jz      short loc_1800108D8
0x180010897  mov     rax, [rdx]
0x18001089a  add     rcx, 18h
0x18001089e  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800108a5  jnz     short loc_1800108B2
0x1800108a7  mov     rax, [rdx+8]
0x1800108ab  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800108b2  test    rax, rax
0x1800108b5  jz      short loc_1800108E5
0x1800108b7  mov     rax, [rcx]
0x1800108ba  mov     rax, [rax+20h]
0x1800108be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c3  mov     edi, eax
0x1800108c5  test    eax, eax
0x1800108c7  js      short loc_1800108EC
0x1800108c9  mov     rcx, [rbx]
0x1800108cc  mov     rdx, [rcx]
0x1800108cf  mov     rax, [rdx+8]
0x1800108d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d8  mov     rbx, [rsp+28h+arg_0]
0x1800108dd  mov     eax, edi
0x1800108df  add     rsp, 20h
0x1800108e3  pop     rdi
0x1800108e4  retn
0x1800108e5  mov     [r8], rcx
0x1800108e8  xor     edi, edi
0x1800108ea  jmp     short loc_1800108C9
0x1800108ec  mov     qword ptr [rbx], 0
0x1800108f3  jmp     short loc_1800108D8
```

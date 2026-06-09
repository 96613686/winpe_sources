# CreateDataObject

- ea: `0x180004f50`
- end: `0x180004fdd`
- name: `CreateDataObject`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f7c`
- `0x180004c64`
- `0x180004f50`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CreateDataObject(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  CDataObject *v8; // rax
  CDataObject *v9; // rax
  CDataObject *v10; // rbx
  __int64 (__fastcall **v11)(CDataObject *, GUID *, __int64); // rcx
  unsigned int v12; // edi

  v8 = (CDataObject *)operator new(0x28u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CDataObject::CDataObject(v8);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  if ( a1 && a2 )
  {
    v11 = *(__int64 (__fastcall ***)(CDataObject *, GUID *, __int64))v9;
    *((_QWORD *)v9 + 2) = a1;
    *((_DWORD *)v9 + 8) = a2;
    *((_QWORD *)v9 + 3) = a3;
    v12 = (*v11)(v9, &IID_IDataObject, a4);
  }
  else
  {
    v12 = -2147024809;
  }
  (*(void (__fastcall **)(CDataObject *))(*(_QWORD *)v10 + 16LL))(v10);
  return v12;
}

```

## disassembly

```asm
0x180004f50  push    rbx
0x180004f52  push    rbp
0x180004f53  push    rsi
0x180004f54  push    rdi
0x180004f55  push    r14
0x180004f57  sub     rsp, 20h
0x180004f5b  mov     rsi, rcx
0x180004f5e  mov     rbp, r9
0x180004f61  mov     ecx, 28h ; '('; Size
0x180004f66  mov     r14, r8
0x180004f69  mov     edi, edx
0x180004f6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f70  test    rax, rax
0x180004f73  jz      short loc_180004FCD
0x180004f75  mov     rcx, rax; this
0x180004f78  call    ??0CDataObject@@QEAA@XZ; CDataObject::CDataObject(void)
0x180004f7d  mov     rbx, rax
0x180004f80  test    rax, rax
0x180004f83  jz      short loc_180004FCD
0x180004f85  test    rsi, rsi
0x180004f88  jz      short loc_180004FB5
0x180004f8a  test    edi, edi
0x180004f8c  jz      short loc_180004FB5
0x180004f8e  mov     rcx, [rax]
0x180004f91  lea     rdx, IID_IDataObject
0x180004f98  mov     [rax+10h], rsi
0x180004f9c  mov     r8, rbp
0x180004f9f  mov     [rax+20h], edi
0x180004fa2  mov     [rax+18h], r14
0x180004fa6  mov     rax, [rcx]
0x180004fa9  mov     rcx, rbx
0x180004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb1  mov     edi, eax
0x180004fb3  jmp     short loc_180004FBA
0x180004fb5  mov     edi, 80070057h
0x180004fba  mov     rax, [rbx]
0x180004fbd  mov     rcx, rbx
0x180004fc0  mov     rax, [rax+10h]
0x180004fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc9  mov     eax, edi
0x180004fcb  jmp     short loc_180004FD2
0x180004fcd  mov     eax, 8007000Eh
0x180004fd2  add     rsp, 20h
0x180004fd6  pop     r14
0x180004fd8  pop     rdi
0x180004fd9  pop     rsi
0x180004fda  pop     rbp
0x180004fdb  pop     rbx
0x180004fdc  retn
```

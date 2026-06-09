# CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(int)

- ea: `0x1800093c0`
- end: `0x18000947b`
- name: `??0CMetadataRDFReaderWriter@@QEAA@H@Z`
- size: `187`
- prototype: `CMetadataRDFReaderWriter *__fastcall(CMetadataRDFReaderWriter *__hidden this, int)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000930c`
- `0x180009a60`
- `0x18000b298`
- `0x18000b358`
- `0x1800142e0`

## callees

- `0x180009484`

## pseudocode

```c
CMetadataRDFReaderWriter *__fastcall CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(
        CMetadataRDFReaderWriter *this,
        int a2)
{
  CMetadataRDFReaderWriter *result; // rax

  CMetadataHandler::CMetadataHandler(this);
  *(_QWORD *)this = &CMetadataRDFReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataRDFReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = a2;
  *((_DWORD *)this + 43) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 30) = 0;
  result = this;
  *((_DWORD *)this + 36) = 2;
  return result;
}

```

## disassembly

```asm
0x1800093c0  mov     [rsp+arg_0], rbx
0x1800093c5  push    rdi
0x1800093c6  sub     rsp, 20h
0x1800093ca  mov     ebx, edx
0x1800093cc  mov     rdi, rcx
0x1800093cf  call    ??0CMetadataHandler@@QEAA@XZ; CMetadataHandler::CMetadataHandler(void)
0x1800093d4  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x1800093db  mov     [rdi], rax
0x1800093de  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x1800093e5  mov     [rdi+8], rax
0x1800093e9  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x1800093f0  mov     [rdi+10h], rax
0x1800093f4  lea     rax, ??_7CMetadataRDFReaderWriter@@6BCMILCOMBase@@@; const CMetadataRDFReaderWriter::`vftable'{for `CMILCOMBase'}
0x1800093fb  mov     [rdi+18h], rax
0x1800093ff  lea     rax, ??_7CMetadataRDFReaderWriter@@6BCMTALock@@@; const CMetadataRDFReaderWriter::`vftable'{for `CMTALock'}
0x180009406  mov     [rdi+28h], rax
0x18000940a  xor     eax, eax
0x18000940c  mov     [rdi+0D0h], rax
0x180009413  mov     [rdi+0D8h], rax
0x18000941a  mov     [rdi+0E0h], rax
0x180009421  mov     [rdi+0E8h], eax
0x180009427  mov     [rdi+98h], rax
0x18000942e  mov     [rdi+0A0h], rax
0x180009435  mov     [rdi+0A8h], ebx
0x18000943b  mov     rbx, [rsp+28h+arg_0]
0x180009440  mov     [rdi+0ACh], eax
0x180009446  mov     [rdi+0B0h], rax
0x18000944d  mov     [rdi+0B8h], rax
0x180009454  mov     [rdi+0C0h], rax
0x18000945b  mov     [rdi+0C8h], eax
0x180009461  mov     [rdi+0F0h], rax
0x180009468  mov     rax, rdi
0x18000946b  mov     dword ptr [rdi+90h], 2
0x180009475  add     rsp, 20h
0x180009479  pop     rdi
0x18000947a  retn
```

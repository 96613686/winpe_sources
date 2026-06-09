# ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)

- ea: `0x180020e74`
- end: `0x180020ef4`
- name: `?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021680`

## callees

- `0x180001d94`
- `0x18000a1c0`
- `0x180020e74`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFileStream>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x20u, a2);
  v5 = v4;
  if ( v4 )
  {
    ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
    *((_QWORD *)v5 + 3) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<CFileStream>::`vftable';
    _InterlockedIncrement(&dword_1800454E8);
  }
  else
  {
    v5 = 0;
  }
  result = v5 == 0 ? 0x8007000E : 0;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x180020e74  mov     [rsp+arg_8], rbx
0x180020e79  push    rdi
0x180020e7a  sub     rsp, 30h
0x180020e7e  mov     rdi, rcx
0x180020e81  test    rcx, rcx
0x180020e84  jnz     short loc_180020E8D
0x180020e86  mov     eax, 80004003h
0x180020e8b  jmp     short loc_180020EE9
0x180020e8d  mov     qword ptr [rcx], 0
0x180020e94  mov     ecx, 20h ; ' '; unsigned int
0x180020e99  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180020e9e  mov     rbx, rax
0x180020ea1  mov     [rsp+38h+arg_0], rax
0x180020ea6  test    rax, rax
0x180020ea9  jz      short loc_180020ECF
0x180020eab  lea     rcx, [rax+8]
0x180020eaf  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180020eb4  mov     qword ptr [rbx+18h], 0
0x180020ebc  lea     rax, ??_7?$CComObject@VCFileStream@@@ATL@@6B@; const ATL::CComObject<CFileStream>::`vftable'
0x180020ec3  mov     [rbx], rax
0x180020ec6  lock inc cs:dword_1800454E8
0x180020ecd  jmp     short loc_180020ED1
0x180020ecf  xor     ebx, ebx
0x180020ed1  mov     rax, rbx
0x180020ed4  neg     rax
0x180020ed7  sbb     eax, eax
0x180020ed9  not     eax
0x180020edb  and     eax, 8007000Eh
0x180020ee0  mov     [rdi], rbx
0x180020ee3  jmp     short loc_180020EE9
0x180020ee5  mov     eax, [rsp+38h+var_18]
0x180020ee9  mov     rbx, [rsp+38h+arg_8]
0x180020eee  add     rsp, 30h
0x180020ef2  pop     rdi
0x180020ef3  retn
```

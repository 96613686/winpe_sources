# ATL::CComObject<CPersistStreamInit>::CreateInstance(ATL::CComObject<CPersistStreamInit> * *)

- ea: `0x180013dec`
- end: `0x180013e9d`
- name: `?CreateInstance@?$CComObject@VCPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800146d0`

## callees

- `0x180001d94`
- `0x18000a1c0`
- `0x180013dec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CPersistStreamInit>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x2058u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 5) = 0;
      *((_QWORD *)v5 + 6) = 0;
      *((_QWORD *)v5 + 7) = 0;
      *((_DWORD *)v5 + 2068) = 0;
      v5[64] = 1;
      *(_QWORD *)v5 = &ATL::CComObject<CPersistStreamInit>::`vftable';
      _InterlockedIncrement(&dword_1800454E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180013dec  mov     [rsp+arg_8], rbx
0x180013df1  push    rdi
0x180013df2  sub     rsp, 30h
0x180013df6  mov     rdi, rcx
0x180013df9  test    rcx, rcx
0x180013dfc  jnz     short loc_180013E08
0x180013dfe  mov     eax, 80004003h
0x180013e03  jmp     loc_180013E92
0x180013e08  mov     qword ptr [rcx], 0
0x180013e0f  mov     ecx, 2058h; unsigned int
0x180013e14  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180013e19  mov     rbx, rax
0x180013e1c  mov     [rsp+38h+arg_0], rax
0x180013e21  test    rax, rax
0x180013e24  jz      short loc_180013E78
0x180013e26  lea     rcx, [rax+8]
0x180013e2a  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180013e2f  mov     qword ptr [rbx+18h], 0
0x180013e37  mov     qword ptr [rbx+20h], 0
0x180013e3f  mov     qword ptr [rbx+28h], 0
0x180013e47  mov     qword ptr [rbx+30h], 0
0x180013e4f  mov     qword ptr [rbx+38h], 0
0x180013e57  mov     dword ptr [rbx+2050h], 0
0x180013e61  mov     byte ptr [rbx+40h], 1
0x180013e65  lea     rax, ??_7?$CComObject@VCPersistStreamInit@@@ATL@@6B@; const ATL::CComObject<CPersistStreamInit>::`vftable'
0x180013e6c  mov     [rbx], rax
0x180013e6f  lock inc cs:dword_1800454E8
0x180013e76  jmp     short loc_180013E7A
0x180013e78  xor     ebx, ebx
0x180013e7a  mov     rax, rbx
0x180013e7d  neg     rax
0x180013e80  sbb     eax, eax
0x180013e82  not     eax
0x180013e84  and     eax, 8007000Eh
0x180013e89  mov     [rdi], rbx
0x180013e8c  jmp     short loc_180013E92
0x180013e8e  mov     eax, [rsp+38h+var_18]
0x180013e92  mov     rbx, [rsp+38h+arg_8]
0x180013e97  add     rsp, 30h
0x180013e9b  pop     rdi
0x180013e9c  retn
```

# AttributeList::setDWordAttribute(ushort *,ulong)

- ea: `0x18000e010`
- end: `0x18000e103`
- name: `?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z`
- size: `243`
- prototype: `void __fastcall(AttributeList *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180002974`
- `0x180005a20`
- `0x1800067d0`

## callees

- `0x18000257c`
- `0x18000a320`
- `0x18000d3d8`
- `0x18000d590`
- `0x18000d750`
- `0x18000e010`
- `0x18000e25c`
- `0x18000eddc`
- `0x18000ee10`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000e0da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AttributeList::setDWordAttribute(void **this, unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // r8d
  __int64 v7; // rbx
  void *v8; // r11
  __int64 v9; // rax
  int pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  int v11; // [rsp+24h] [rbp-54h] BYREF
  __int128 v12; // [rsp+28h] [rbp-50h]
  __int64 v13; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *TestMemory; // [rsp+80h] [rbp+8h] BYREF
  HANDLE v15; // [rsp+98h] [rbp+20h] BYREF

  if ( (unsigned int)AttributeList::attributeExists(this, a2, a3) )
    AttributeList::unsetAttribute(this, a2, v6);
  AutoMutex::AutoMutex((AutoMutex *)&v15, this[2], v6);
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  *(_QWORD *)&v12 = 2;
  HIDWORD(v12) = 0;
  TestMemory = (unsigned __int16 *)AllocateTestMemory(2 * v7 + 2);
  if ( (unsigned int)StringCchCopyW(TestMemory, v7 + 1, a2) )
  {
    FreeTestMemory(v8);
    pExceptionObject = 4;
    throw (TestException *)&pExceptionObject;
  }
  DWORD2(v12) = a3;
  try
  {
    v9 = std::map<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>>::operator[](
           this,
           &TestMemory);
    *(_OWORD *)v9 = v12;
    *(_QWORD *)(v9 + 16) = 0;
  }
  catch ( exception v13 )
  {
    FreeTestMemory(TestMemory);
    v11 = 0;
    throw (TestException *)&v11;
  }
  ReleaseMutex(v15);
}

```

## disassembly

```asm
0x18000e010  mov     [rsp+arg_8], rbx
0x18000e015  mov     [rsp+arg_10], rsi
0x18000e01a  push    rdi
0x18000e01b  push    r14
0x18000e01d  push    r15
0x18000e01f  sub     rsp, 60h
0x18000e023  mov     r14d, r8d
0x18000e026  mov     rsi, rdx
0x18000e029  mov     rdi, rcx
0x18000e02c  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000e031  xor     r15d, r15d
0x18000e034  test    eax, eax
0x18000e036  jz      short loc_18000E043
0x18000e038  mov     rdx, rsi; unsigned __int16 *
0x18000e03b  mov     rcx, rdi; this
0x18000e03e  call    ?unsetAttribute@AttributeList@@QEAAXPEAG@Z; AttributeList::unsetAttribute(ushort *)
0x18000e043  mov     rdx, [rdi+10h]; void *
0x18000e047  lea     rcx, [rsp+78h+arg_18]; this
0x18000e04f  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000e054  nop
0x18000e055  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e059  inc     rbx
0x18000e05c  cmp     [rsi+rbx*2], r15w
0x18000e061  jnz     short loc_18000E059
0x18000e063  mov     qword ptr [rsp+78h+var_50], 2
0x18000e06c  mov     dword ptr [rsp+78h+var_50+0Ch], r15d
0x18000e071  lea     rcx, ds:2[rbx*2]; unsigned __int64
0x18000e079  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e07e  mov     r11, rax
0x18000e081  mov     [rsp+78h+arg_0], rax
0x18000e089  lea     rdx, [rbx+1]; unsigned __int64
0x18000e08d  mov     r8, rsi; unsigned __int16 *
0x18000e090  mov     rcx, rax; unsigned __int16 *
0x18000e093  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e098  test    eax, eax
0x18000e09a  jnz     short loc_18000E0E1
0x18000e09c  mov     dword ptr [rsp+78h+var_50+8], r14d
0x18000e0a1  lea     rdx, [rsp+78h+arg_0]
0x18000e0a9  mov     rcx, rdi
0x18000e0ac  call    ??A?$map@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@QEAAAEAUAttribute@@AEBQEAG@Z; std::map<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>>::operator[](ushort * const &)
0x18000e0b1  movups  xmm0, [rsp+78h+var_50]
0x18000e0b6  movups  xmmword ptr [rax], xmm0
0x18000e0b9  mov     [rax+10h], r15
0x18000e0bd  mov     rcx, [rsp+78h+arg_18]
0x18000e0c5  lea     r11, [rsp+78h+var_18]
0x18000e0ca  mov     rbx, [r11+28h]
0x18000e0ce  mov     rsi, [r11+30h]
0x18000e0d2  mov     rsp, r11
0x18000e0d5  pop     r15
0x18000e0d7  pop     r14
0x18000e0d9  pop     rdi
0x18000e0da  jmp     cs:__imp_ReleaseMutex
0x18000e0e1  mov     rcx, r11; pv
0x18000e0e4  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e0e9  mov     [rsp+78h+pExceptionObject], 4
0x18000e0f1  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e0f8  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000e0fd  call    _CxxThrowException_0
```

# AttributeList::setStringAttribute(ushort *,ushort *)

- ea: `0x18000e10c`
- end: `0x18000e253`
- name: `?setStringAttribute@AttributeList@@QEAAXPEAG0@Z`
- size: `327`
- prototype: `void(AttributeList *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180002974`
- `0x1800051b4`
- `0x180005a20`
- `0x180008440`
- `0x1800088e0`
- `0x18000a690`

## callees

- `0x18000257c`
- `0x18000a320`
- `0x18000d3d8`
- `0x18000d590`
- `0x18000e10c`
- `0x18000eddc`
- `0x18000ee10`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000e1fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AttributeList::setStringAttribute(void **this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rsi
  LPVOID TestMemory; // rax
  void *v9; // r14
  void *v10; // rbx
  int v11; // eax
  unsigned __int64 v12; // rdi
  __int64 v13; // rax
  void *v14; // rcx
  int pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  int v16; // [rsp+24h] [rbp-74h] BYREF
  int v17; // [rsp+28h] [rbp-70h] BYREF
  int v18; // [rsp+2Ch] [rbp-6Ch] BYREF
  int v19; // [rsp+30h] [rbp-68h] BYREF
  __int128 v20; // [rsp+38h] [rbp-60h]
  __int64 v21; // [rsp+50h] [rbp-48h] BYREF
  LPVOID v22; // [rsp+A0h] [rbp+8h] BYREF
  void *v23; // [rsp+B8h] [rbp+20h] BYREF

  AutoMutex::AutoMutex((AutoMutex *)&v23, this[2], (unsigned int)a3);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  do
    ++v6;
  while ( a3[v6] );
  v20 = 0;
  LODWORD(v20) = 1;
  TestMemory = AllocateTestMemory(2 * v6 + 2);
  try
  {
    v9 = TestMemory;
    *((_QWORD *)&v20 + 1) = TestMemory;
    v10 = AllocateTestMemory(2 * v7 + 2);
    v22 = v10;
    v11 = StringCchCopyW((unsigned __int16 *)v10, v7 + 1, a2);
  }
  catch ( TestException v19 )
  {
    FreeTestMemory(*((LPVOID *)&v20 + 1));
    v18 = v19;
    throw (TestException *)&v18;
  }
  if ( v11 )
  {
    FreeTestMemory(v9);
    FreeTestMemory(v10);
    pExceptionObject = 4;
    throw (TestException *)&pExceptionObject;
  }
  v12 = v6 + 1;
  if ( (unsigned int)StringCchCopyW((unsigned __int16 *)v9, v12, a3) )
  {
    FreeTestMemory(v9);
    FreeTestMemory(v10);
    v16 = 4;
    throw (TestException *)&v16;
  }
  try
  {
    v13 = std::map<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>>::operator[](
            this,
            &v22);
    *(_OWORD *)v13 = v20;
    *(_QWORD *)(v13 + 16) = v12;
    v14 = v23;
  }
  catch ( exception v21 )
  {
    FreeTestMemory(*((LPVOID *)&v20 + 1));
    FreeTestMemory(v22);
    v17 = 0;
    throw (TestException *)&v17;
  }
  ReleaseMutex(v14);
}

```

## disassembly

```asm
0x18000e10c  mov     rax, rsp
0x18000e10f  mov     [rax+10h], rbx
0x18000e113  mov     [rax+18h], rsi
0x18000e117  push    rdi
0x18000e118  push    r12
0x18000e11a  push    r13
0x18000e11c  push    r14
0x18000e11e  push    r15
0x18000e120  sub     rsp, 70h
0x18000e124  mov     r12, r8
0x18000e127  mov     r15, rdx
0x18000e12a  mov     r13, rcx
0x18000e12d  mov     rdx, [rcx+10h]; void *
0x18000e131  lea     rcx, [rax+20h]; this
0x18000e135  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000e13a  nop
0x18000e13b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e13f  mov     rsi, rdi
0x18000e142  xor     eax, eax
0x18000e144  inc     rsi
0x18000e147  cmp     [r15+rsi*2], ax
0x18000e14c  jnz     short loc_18000E144
0x18000e14e  inc     rdi
0x18000e151  cmp     [r12+rdi*2], ax
0x18000e156  jnz     short loc_18000E14E
0x18000e158  xorps   xmm0, xmm0
0x18000e15b  movups  [rsp+98h+var_60], xmm0
0x18000e160  mov     dword ptr [rsp+98h+var_60], 1
0x18000e168  lea     rcx, ds:2[rdi*2]; unsigned __int64
0x18000e170  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e175  mov     r14, rax
0x18000e178  mov     qword ptr [rsp+98h+var_60+8], rax
0x18000e17d  lea     rcx, ds:2[rsi*2]; unsigned __int64
0x18000e185  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e18a  mov     rbx, rax
0x18000e18d  mov     [rsp+98h+arg_0], rax
0x18000e195  lea     rdx, [rsi+1]; unsigned __int64
0x18000e199  mov     r8, r15; unsigned __int16 *
0x18000e19c  mov     rcx, rbx; unsigned __int16 *
0x18000e19f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1a4  mov     rcx, r14; unsigned __int16 *
0x18000e1a7  test    eax, eax
0x18000e1a9  jnz     short loc_18000E201
0x18000e1ab  inc     rdi
0x18000e1ae  mov     r8, r12; unsigned __int16 *
0x18000e1b1  mov     rdx, rdi; unsigned __int64
0x18000e1b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1b9  test    eax, eax
0x18000e1bb  jnz     short loc_18000E229
0x18000e1bd  lea     rdx, [rsp+98h+arg_0]
0x18000e1c5  mov     rcx, r13
0x18000e1c8  call    ??A?$map@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@QEAAAEAUAttribute@@AEBQEAG@Z; std::map<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>>::operator[](ushort * const &)
0x18000e1cd  movups  xmm0, [rsp+98h+var_60]
0x18000e1d2  movups  xmmword ptr [rax], xmm0
0x18000e1d5  mov     [rax+10h], rdi
0x18000e1d9  mov     rcx, [rsp+98h+arg_18]
0x18000e1e1  lea     r11, [rsp+98h+var_28]
0x18000e1e6  mov     rbx, [r11+38h]
0x18000e1ea  mov     rsi, [r11+40h]
0x18000e1ee  mov     rsp, r11
0x18000e1f1  pop     r15
0x18000e1f3  pop     r14
0x18000e1f5  pop     r13
0x18000e1f7  pop     r12
0x18000e1f9  pop     rdi
0x18000e1fa  jmp     cs:__imp_ReleaseMutex
0x18000e201  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e206  nop
0x18000e207  mov     rcx, rbx; pv
0x18000e20a  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e20f  mov     [rsp+98h+pExceptionObject], 4
0x18000e217  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e21e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e223  call    _CxxThrowException_0
0x18000e229  mov     rcx, r14; pv
0x18000e22c  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e231  mov     rcx, rbx; pv
0x18000e234  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e239  mov     [rsp+98h+var_74], 4
0x18000e241  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e248  lea     rcx, [rsp+98h+var_74]; pExceptionObject
0x18000e24d  call    _CxxThrowException_0
```

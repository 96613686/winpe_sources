# ConfigPathNavigationTree::AddVDirMappingOwner(ushort const *,ConfigPathTagNode *)

- ea: `0x18000c5a4`
- end: `0x18000c67d`
- name: `?AddVDirMappingOwner@ConfigPathNavigationTree@@QEAAXPEBGPEAVConfigPathTagNode@@@Z`
- size: `217`
- prototype: `void __fastcall(ConfigPathNavigationTree *__hidden this, const unsigned __int16 *, struct ConfigPathTagNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d9ac`

## callees

- `0x180001194`
- `0x18000a2fc`
- `0x18000c5a4`
- `0x1800126b0`
- `0x18001277c`
- `0x180012f3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConfigPathNavigationTree::AddVDirMappingOwner(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        struct ConfigPathTagNode *a3)
{
  int v5; // eax
  _QWORD *v6; // rbx
  __int64 v7; // rax
  int inserted; // eax
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  _QWORD *pExceptionObject; // [rsp+78h] [rbp+40h] BYREF

  v9[0] = 0;
  v5 = String::Initialize((String *)v9, a2);
  if ( v5 < 0 )
  {
    LODWORD(pExceptionObject) = v5;
    throw (long *)&pExceptionObject;
  }
  v6 = operator new(0x10u);
  pExceptionObject = v6;
  if ( v6 )
  {
    v7 = v9[0];
    pExceptionObject = (_QWORD *)v9[0];
    if ( v9[0] )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v9[0] - 8LL));
      *v6 = v7;
      _InterlockedIncrement((volatile signed __int32 *)(v7 - 8));
    }
    else
    {
      *v6 = 0;
    }
    v6[1] = a3;
    String::Reset((String *)&pExceptionObject);
  }
  else
  {
    v6 = 0;
  }
  v9[1] = v6;
  if ( !v6 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  inserted = HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::InsertRecord(this + 21, (__int64)v6);
  if ( inserted < 0 )
  {
    LODWORD(pExceptionObject) = inserted;
    throw (long *)&pExceptionObject;
  }
  String::Reset((String *)v9);
}

```

## disassembly

```asm
0x18000c5a4  push    rbp
0x18000c5a6  push    rbx
0x18000c5a7  push    rsi
0x18000c5a8  push    rdi
0x18000c5a9  mov     rbp, rsp
0x18000c5ac  sub     rsp, 38h
0x18000c5b0  mov     rdi, r8
0x18000c5b3  mov     rsi, rcx
0x18000c5b6  mov     [rbp+var_18], 0
0x18000c5be  lea     rcx, [rbp+var_18]; this
0x18000c5c2  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000c5c7  test    eax, eax
0x18000c5c9  jns     short loc_18000C5DF
0x18000c5cb  mov     dword ptr [rbp+pExceptionObject], eax
0x18000c5ce  lea     rdx, _TI1J; pThrowInfo
0x18000c5d5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c5d9  call    _CxxThrowException_0
0x18000c5df  mov     ecx, 10h; Size
0x18000c5e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c5e9  mov     rbx, rax
0x18000c5ec  mov     [rbp+pExceptionObject], rax
0x18000c5f0  test    rax, rax
0x18000c5f3  jz      short loc_18000C621
0x18000c5f5  mov     rax, [rbp+var_18]
0x18000c5f9  mov     [rbp+pExceptionObject], rax
0x18000c5fd  test    rax, rax
0x18000c600  jz      short loc_18000C60F
0x18000c602  lock inc dword ptr [rax-8]
0x18000c606  mov     [rbx], rax
0x18000c609  lock inc dword ptr [rax-8]
0x18000c60d  jmp     short loc_18000C612
0x18000c60f  mov     [rbx], rax
0x18000c612  mov     [rbx+8], rdi
0x18000c616  lea     rcx, [rbp+pExceptionObject]; this
0x18000c61a  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c61f  jmp     short loc_18000C623
0x18000c621  xor     ebx, ebx
0x18000c623  mov     [rbp+var_10], rbx
0x18000c627  test    rbx, rbx
0x18000c62a  jnz     short loc_18000C644
0x18000c62c  mov     dword ptr [rbp+pExceptionObject], 8007000Eh
0x18000c633  lea     rdx, _TI1J; pThrowInfo
0x18000c63a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c63e  call    _CxxThrowException_0
0x18000c644  lea     rcx, [rsi+0A8h]
0x18000c64b  mov     rdx, rbx
0x18000c64e  call    ?InsertRecord@?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@QEAAJPEAVVDirMappingOwnerDescriptor@@@Z; HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::InsertRecord(VDirMappingOwnerDescriptor *)
0x18000c653  test    eax, eax
0x18000c655  jns     short loc_18000C66B
0x18000c657  mov     dword ptr [rbp+pExceptionObject], eax
0x18000c65a  lea     rdx, _TI1J; pThrowInfo
0x18000c661  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c665  call    _CxxThrowException_0
0x18000c66b  lea     rcx, [rbp+var_18]; this
0x18000c66f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c674  add     rsp, 38h
0x18000c678  pop     rdi
0x18000c679  pop     rsi
0x18000c67a  pop     rbx
0x18000c67b  pop     rbp
0x18000c67c  retn
```

# ListKnownKeys

- ea: `0x18001241c`
- end: `0x1800125ce`
- name: `ListKnownKeys`
- size: `434`
- prototype: `_BOOL8 __fastcall(__int64, struct CBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800174e8`

## callees

- `0x18001241c`
- `0x1800125e0`
- `0x1800176a8`
- `0x180018a68`
- `0x18001a328`
- `0x180023168`
- `0x180032398`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012587`
- `KERNEL32!lstrlenW` at `0x1800124e7`
- `KERNEL32!lstrlenW` at `0x1800124e7`

## string_xrefs

- `0x180012473`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
_BOOL8 __fastcall ListKnownKeys(__int64 a1, struct CBuffer *a2)
{
  __int64 i; // rbx
  __int64 j; // rdi
  unsigned int v4; // r15d
  unsigned int k; // edx
  int v6; // eax
  const WCHAR *v7; // rax
  const unsigned __int8 *v8; // rsi
  const unsigned __int16 *v9; // rbx
  void *v10; // rdi
  BOOL v11; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-39h]
  void **v14; // [rsp+40h] [rbp-29h] BYREF
  void *Block; // [rsp+48h] [rbp-21h]
  __int64 v16; // [rsp+50h] [rbp-19h]
  HKEY hKey[2]; // [rsp+58h] [rbp-11h] BYREF
  void **v18; // [rsp+68h] [rbp-1h]
  void *v19; // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+80h] [rbp+17h]

  v18 = &CBuffer::`vftable';
  v19 = 0;
  v20 = 0;
  hKey[0] = 0;
  v21 = 1010;
  v14 = &CBuffer::`vftable';
  Block = 0;
  v16 = 0;
  lpSubKey[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers";
  lpSubKey[1] = 0;
  for ( i = 0; i != 2; ++i )
  {
    if ( lpSubKey[i] )
    {
      for ( j = 0; j != 2; ++j )
      {
        if ( LODWORD(qword_18003C880[2 * j]) >= 2 )
        {
          CRegistry::Open((DWORD *)hKey, (HKEY)qword_18003C880[2 * j + 1], lpSubKey[i], 0x20019u, 0xFFFFFFE0);
          if ( !(unsigned int)CRegistry::Status((CRegistry *)hKey, 1) )
          {
            v4 = 0;
            for ( k = 0; ; k = v4 )
            {
              v7 = CRegistry::Subkey((CRegistry *)hKey, k);
              v8 = (const unsigned __int8 *)v7;
              if ( !v7 )
                break;
              v6 = lstrlenW(v7);
              CBuffer::Append((CBuffer *)&v14, v8, 2 * v6 + 2);
              ++v4;
            }
          }
        }
      }
    }
  }
  v9 = &Data;
  CBuffer::Append((CBuffer *)&v14, (const unsigned __int8 *const)&Data, 4u);
  v10 = Block;
  if ( HIDWORD(v16) )
    v9 = (const unsigned __int16 *)Block;
  MStringSort(v9, a2);
  v11 = *((_DWORD *)a2 + 4) > 4u;
  if ( v10 )
    operator delete[](v10);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  v21 = 1010;
  LODWORD(v20) = 0;
  v18 = &CBuffer::`vftable';
  if ( v19 )
    operator delete[](v19);
  return v11;
}

```

## disassembly

```asm
0x18001241c  mov     [rsp-8+arg_8], rdx
0x180012421  push    rbp
0x180012422  push    rbx
0x180012423  push    rsi
0x180012424  push    rdi
0x180012425  push    r12
0x180012427  push    r15
0x180012429  lea     rbp, [rsp-2Fh]
0x18001242e  sub     rsp, 98h
0x180012435  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001243c  mov     [rbp+57h+var_58], rax
0x180012440  mov     [rbp+57h+var_50], 0
0x180012448  mov     [rbp+57h+var_48], 0
0x180012450  mov     [rbp+57h+hKey], 0
0x180012458  mov     [rbp+57h+var_40], 3F2h
0x18001245f  mov     [rbp+57h+var_80], rax
0x180012463  mov     [rbp+57h+Block], 0
0x18001246b  mov     [rbp+57h+var_70], 0
0x180012473  lea     rax, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18001247a  mov     [rbp+57h+lpSubKey], rax
0x18001247e  mov     [rbp+57h+var_88], 0
0x180012486  xor     ebx, ebx
0x180012488  lea     r12, qword_18003C880
0x18001248f  cmp     [rbp+rbx*8+57h+lpSubKey], 0
0x180012495  jz      loc_180012525
0x18001249b  xor     edi, edi
0x18001249d  mov     rdx, rdi
0x1800124a0  add     rdx, rdx
0x1800124a3  cmp     dword ptr [r12+rdx*8], 2
0x1800124a8  jb      short loc_180012518
0x1800124aa  mov     [rsp+0C0h+dwOptions], 0FFFFFFE0h; dwOptions
0x1800124b2  mov     r9d, 20019h; samDesired
0x1800124b8  mov     r8, [rbp+rbx*8+57h+lpSubKey]; lpSubKey
0x1800124bd  mov     rdx, [r12+rdx*8+8]; hKey
0x1800124c2  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800124c6  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1800124cb  mov     edx, 1; int
0x1800124d0  lea     rcx, [rbp+57h+hKey]; this
0x1800124d4  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x1800124d9  test    eax, eax
0x1800124db  jnz     short loc_180012518
0x1800124dd  xor     r15d, r15d
0x1800124e0  xor     edx, edx
0x1800124e2  jmp     short loc_180012507
0x1800124e4  mov     rcx, rsi; lpString
0x1800124e7  call    cs:__imp_lstrlenW
0x1800124ed  lea     r8d, ds:2[rax*2]; unsigned int
0x1800124f5  mov     rdx, rsi; unsigned __int8 *
0x1800124f8  lea     rcx, [rbp+57h+var_80]; this
0x1800124fc  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x180012501  inc     r15d
0x180012504  mov     edx, r15d; unsigned int
0x180012507  lea     rcx, [rbp+57h+hKey]; this
0x18001250b  call    ?Subkey@CRegistry@@QEAAPEBGK@Z; CRegistry::Subkey(ulong)
0x180012510  test    rax, rax
0x180012513  mov     rsi, rax
0x180012516  jnz     short loc_1800124E4
0x180012518  inc     rdi
0x18001251b  cmp     rdi, 2
0x18001251f  jnz     loc_18001249D
0x180012525  inc     rbx
0x180012528  cmp     rbx, 2
0x18001252c  jnz     loc_18001248F
0x180012532  lea     r8d, [rbx+2]; unsigned int
0x180012536  lea     rbx, Data
0x18001253d  mov     rdx, rbx; unsigned __int8 *
0x180012540  lea     rcx, [rbp+57h+var_80]; this
0x180012544  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x180012549  mov     rdi, [rbp+57h+Block]
0x18001254d  cmp     dword ptr [rbp+57h+var_70+4], 0
0x180012551  cmova   rbx, rdi
0x180012555  mov     r12, [rbp+57h+arg_8]
0x180012559  mov     rdx, r12; struct CBuffer *
0x18001255c  mov     rcx, rbx; unsigned __int16 *
0x18001255f  call    ?MStringSort@@YAKPEBGAEAVCBuffer@@@Z; MStringSort(ushort const *,CBuffer &)
0x180012564  nop
0x180012565  xor     ebx, ebx
0x180012567  cmp     dword ptr [r12+10h], 4
0x18001256d  setnbe  bl
0x180012570  test    rdi, rdi
0x180012573  jz      short loc_18001257E
0x180012575  mov     rcx, rdi; Block
0x180012578  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001257d  nop
0x18001257e  mov     rcx, [rbp+57h+hKey]; hKey
0x180012582  test    rcx, rcx
0x180012585  jz      short loc_180012595
0x180012587  call    cs:__imp_RegCloseKey
0x18001258d  mov     [rbp+57h+hKey], 0
0x180012595  mov     [rbp+57h+var_40], 3F2h
0x18001259c  mov     dword ptr [rbp+57h+var_48], 0
0x1800125a3  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800125aa  mov     [rbp+57h+var_58], rax
0x1800125ae  mov     rcx, [rbp+57h+var_50]; Block
0x1800125b2  test    rcx, rcx
0x1800125b5  jz      short loc_1800125BC
0x1800125b7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800125bc  mov     eax, ebx
0x1800125be  add     rsp, 98h
0x1800125c5  pop     r15
0x1800125c7  pop     r12
0x1800125c9  pop     rdi
0x1800125ca  pop     rsi
0x1800125cb  pop     rbx
0x1800125cc  pop     rbp
0x1800125cd  retn
```

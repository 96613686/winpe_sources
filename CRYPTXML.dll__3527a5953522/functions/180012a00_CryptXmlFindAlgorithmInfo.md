# CryptXmlFindAlgorithmInfo

- ea: `0x180012a00`
- end: `0x180012ad3`
- name: `CryptXmlFindAlgorithmInfo`
- size: `211`
- prototype: `const CRYPT_XML_ALGORITHM_INFO *__stdcall(DWORD dwFindByType, const void *pvFindBy, DWORD dwGroupId, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f200`
- `0x180012a00`
- `0x180012c64`

## pseudocode

```c
const CRYPT_XML_ALGORITHM_INFO *__stdcall CryptXmlFindAlgorithmInfo(
        DWORD dwFindByType,
        const void *pvFindBy,
        DWORD dwGroupId,
        DWORD dwFlags)
{
  const CRYPT_XML_ALGORITHM_INFO *v4; // rdi
  PCNZWCH **v9; // rcx
  __int64 i; // rbx
  __int64 j; // rbx

  v4 = 0;
  if ( !dword_180022FC8 )
    LoadRegExtensions();
  if ( pvFindBy )
  {
    if ( (dwFlags & 0x10000000) == 0 )
    {
      v9 = (PCNZWCH **)qword_180022FD8;
      for ( i = 0; (unsigned int)i < dword_180022FC0; i = (unsigned int)(i + 1) )
      {
        if ( !dwGroupId || dwGroupId == *((_DWORD *)v9[i] + 6) )
        {
          if ( (unsigned int)CompareAlgInfo(v9[i], dwFindByType, (__int64)pvFindBy) )
            return (const CRYPT_XML_ALGORITHM_INFO *)*((_QWORD *)qword_180022FD8 + i);
          v9 = (PCNZWCH **)qword_180022FD8;
        }
      }
    }
    for ( j = 0; (unsigned int)j < 0x11; j = (unsigned int)(j + 1) )
    {
      if ( (!dwGroupId || dwGroupId == LODWORD(qword_180022180[9 * j + 3]))
        && (unsigned int)CompareAlgInfo((PCNZWCH *)&qword_180022180[9 * j], dwFindByType, (__int64)pvFindBy) )
      {
        return (const CRYPT_XML_ALGORITHM_INFO *)&qword_180022180[9 * j];
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180012a00  push    rbx
0x180012a02  push    rbp
0x180012a03  push    rsi
0x180012a04  push    rdi
0x180012a05  push    r12
0x180012a07  push    r14
0x180012a09  push    r15
0x180012a0b  sub     rsp, 20h
0x180012a0f  xor     edi, edi
0x180012a11  mov     ebx, r9d
0x180012a14  cmp     cs:dword_180022FC8, edi
0x180012a1a  mov     esi, r8d
0x180012a1d  mov     r14, rdx
0x180012a20  mov     r15d, ecx
0x180012a23  jnz     short loc_180012A2A
0x180012a25  call    _LoadRegExtensions
0x180012a2a  test    r14, r14
0x180012a2d  jz      loc_180012AC0
0x180012a33  bt      ebx, 1Ch
0x180012a37  jb      short loc_180012A82
0x180012a39  mov     rcx, cs:qword_180022FD8
0x180012a40  xor     ebx, ebx
0x180012a42  cmp     ebx, cs:dword_180022FC0
0x180012a48  jnb     short loc_180012A82
0x180012a4a  test    esi, esi
0x180012a4c  jz      short loc_180012A57
0x180012a4e  mov     rdx, [rcx+rbx*8]
0x180012a52  cmp     esi, [rdx+18h]
0x180012a55  jnz     short loc_180012A71
0x180012a57  mov     rcx, [rcx+rbx*8]
0x180012a5b  mov     r8, r14
0x180012a5e  mov     edx, r15d
0x180012a61  call    _CompareAlgInfo
0x180012a66  test    eax, eax
0x180012a68  jnz     short loc_180012A75
0x180012a6a  mov     rcx, cs:qword_180022FD8
0x180012a71  inc     ebx
0x180012a73  jmp     short loc_180012A42
0x180012a75  mov     rax, cs:qword_180022FD8
0x180012a7c  mov     rdi, [rax+rbx*8]
0x180012a80  jmp     short loc_180012AC0
0x180012a82  xor     ebx, ebx
0x180012a84  lea     r12, qword_180022180
0x180012a8b  cmp     ebx, 11h
0x180012a8e  jnb     short loc_180012AC0
0x180012a90  test    esi, esi
0x180012a92  jz      short loc_180012A9F
0x180012a94  lea     rcx, [rbx+rbx*8]
0x180012a98  cmp     esi, [r12+rcx*8+18h]
0x180012a9d  jnz     short loc_180012AB9
0x180012a9f  lea     rcx, [rbx+rbx*8]
0x180012aa3  mov     r8, r14
0x180012aa6  lea     rbp, [r12+rcx*8]
0x180012aaa  mov     edx, r15d
0x180012aad  mov     rcx, rbp
0x180012ab0  call    _CompareAlgInfo
0x180012ab5  test    eax, eax
0x180012ab7  jnz     short loc_180012ABD
0x180012ab9  inc     ebx
0x180012abb  jmp     short loc_180012A8B
0x180012abd  mov     rdi, rbp
0x180012ac0  mov     rax, rdi
0x180012ac3  add     rsp, 20h
0x180012ac7  pop     r15
0x180012ac9  pop     r14
0x180012acb  pop     r12
0x180012acd  pop     rdi
0x180012ace  pop     rsi
0x180012acf  pop     rbp
0x180012ad0  pop     rbx
0x180012ad1  retn
```

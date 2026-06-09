# CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)

- ea: `0x1800d445c`
- end: `0x1800d45b6`
- name: `?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z`
- size: `346`
- prototype: `int(CAceList *__hidden this, struct CAce *const, bool, struct _ACL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d3f2c`

## callees

- `0x18003aa84`
- `0x180056c06`
- `0x1800d445c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d454f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d454f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4567`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4567`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d449d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d449d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d44d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d4513`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d44d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d4513`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800d44e7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800d44e7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800d4588`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800d4588`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800d4545`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800d4545`

## pseudocode

```c
__int64 __fastcall CAceList::_AddAllowedAceToAcl(CAceList *this, struct CAce *const a2, char a3, struct _ACL *a4)
{
  unsigned __int8 v6; // bl
  char *v7; // rax
  char *v8; // r15
  unsigned int Error; // esi
  void *v10; // rbx
  DWORD LengthSid; // eax
  const void *v12; // rdi
  unsigned int v13; // ebx
  DWORD v14; // eax
  signed int LastError; // eax
  signed int v16; // eax

  if ( !a3 || *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
    v6 = *((_BYTE *)a2 + 1);
  else
    v6 = *((_BYTE *)a2 + 1) & 0xEF;
  if ( *(_BYTE *)a2 == 9 )
  {
    v7 = (char *)LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 1));
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    *v7 = *(_BYTE *)a2;
    v7[1] = v6;
    *((_WORD *)v7 + 1) = *((_WORD *)a2 + 1);
    *((_DWORD *)v7 + 1) = *((_DWORD *)a2 + 1);
    v10 = (void *)*((_QWORD *)a2 + 1);
    LengthSid = GetLengthSid(v10);
    if ( CopySid(LengthSid, v8 + 8, v10) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( (Error & 0x80000000) != 0 )
      {
LABEL_17:
        LocalFree(v8);
        return Error;
      }
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      v12 = (const void *)*((_QWORD *)a2 + 2);
      v13 = *((_DWORD *)a2 + 6);
      v14 = GetLengthSid(*((PSID *)a2 + 1));
      memcpy_0(&v8[v14 + 8], v12, v13);
    }
    if ( !AddAce(a4, 2u, 0xFFFFFFFF, v8, *((unsigned __int16 *)a2 + 1)) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_17;
  }
  Error = 0;
  if ( !AddAccessAllowedAceEx(a4, 2u, v6, *((_DWORD *)a2 + 1), *((PSID *)a2 + 1)) )
  {
    v16 = GetLastError();
    Error = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return Error;
}

```

## disassembly

```asm
0x1800d445c  push    rbx
0x1800d445e  push    rbp
0x1800d445f  push    rsi
0x1800d4460  push    rdi
0x1800d4461  push    r14
0x1800d4463  push    r15
0x1800d4465  sub     rsp, 38h
0x1800d4469  mov     rbp, r9
0x1800d446c  mov     r14, rdx
0x1800d446f  test    r8b, r8b
0x1800d4472  jz      short loc_1800D4488
0x1800d4474  cmp     dword ptr [rcx+18h], 0
0x1800d4478  jnz     short loc_1800D4488
0x1800d447a  cmp     dword ptr [rcx+1Ch], 0
0x1800d447e  jnz     short loc_1800D4488
0x1800d4480  mov     bl, [rdx+1]
0x1800d4483  and     bl, 0EFh
0x1800d4486  jmp     short loc_1800D448B
0x1800d4488  mov     bl, [rdx+1]
0x1800d448b  cmp     byte ptr [rdx], 9
0x1800d448e  jnz     loc_1800D456F
0x1800d4494  movzx   edx, word ptr [rdx+2]; uBytes
0x1800d4498  mov     ecx, 40h ; '@'; uFlags
0x1800d449d  call    cs:__imp_LocalAlloc
0x1800d44a3  mov     r15, rax
0x1800d44a6  test    rax, rax
0x1800d44a9  jnz     short loc_1800D44B5
0x1800d44ab  mov     esi, 8007000Eh
0x1800d44b0  jmp     loc_1800D45A7
0x1800d44b5  mov     al, [r14]
0x1800d44b8  mov     [r15], al
0x1800d44bb  mov     [r15+1], bl
0x1800d44bf  movzx   eax, word ptr [r14+2]
0x1800d44c4  mov     [r15+2], ax
0x1800d44c9  mov     eax, [r14+4]
0x1800d44cd  mov     [r15+4], eax
0x1800d44d1  mov     rbx, [r14+8]
0x1800d44d5  mov     rcx, rbx; pSid
0x1800d44d8  call    cs:__imp_GetLengthSid
0x1800d44de  lea     rdx, [r15+8]; pDestinationSid
0x1800d44e2  mov     r8, rbx; pSourceSid
0x1800d44e5  mov     ecx, eax; nDestinationSidLength
0x1800d44e7  call    cs:__imp_CopySid
0x1800d44ed  test    eax, eax
0x1800d44ef  jz      short loc_1800D44F5
0x1800d44f1  xor     esi, esi
0x1800d44f3  jmp     short loc_1800D4500
0x1800d44f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d44fa  mov     esi, eax
0x1800d44fc  test    eax, eax
0x1800d44fe  js      short loc_1800D4564
0x1800d4500  cmp     dword ptr [r14+18h], 0
0x1800d4505  jz      short loc_1800D452D
0x1800d4507  mov     rcx, [r14+8]; pSid
0x1800d450b  mov     rdi, [r14+10h]
0x1800d450f  mov     ebx, [r14+18h]
0x1800d4513  call    cs:__imp_GetLengthSid
0x1800d4519  mov     ecx, eax
0x1800d451b  mov     r8d, ebx; Size
0x1800d451e  add     rcx, 8
0x1800d4522  mov     rdx, rdi; Src
0x1800d4525  add     rcx, r15; void *
0x1800d4528  call    memcpy_0
0x1800d452d  movzx   eax, word ptr [r14+2]
0x1800d4532  mov     r9, r15; pAceList
0x1800d4535  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800d4539  mov     [rsp+68h+nAceListLength], eax; nAceListLength
0x1800d453d  mov     edx, 2; dwAceRevision
0x1800d4542  mov     rcx, rbp; pAcl
0x1800d4545  call    cs:__imp_AddAce
0x1800d454b  test    eax, eax
0x1800d454d  jnz     short loc_1800D4564
0x1800d454f  call    cs:__imp_GetLastError
0x1800d4555  mov     esi, eax
0x1800d4557  test    eax, eax
0x1800d4559  jle     short loc_1800D4564
0x1800d455b  movzx   esi, ax
0x1800d455e  or      esi, 80070000h
0x1800d4564  mov     rcx, r15; hMem
0x1800d4567  call    cs:__imp_LocalFree
0x1800d456d  jmp     short loc_1800D45A7
0x1800d456f  mov     rax, [rdx+8]
0x1800d4573  xor     esi, esi
0x1800d4575  mov     r9d, [rdx+4]; AccessMask
0x1800d4579  mov     rcx, rbp; pAcl
0x1800d457c  movzx   r8d, bl; AceFlags
0x1800d4580  mov     qword ptr [rsp+68h+nAceListLength], rax; pSid
0x1800d4585  lea     edx, [rsi+2]; dwAceRevision
0x1800d4588  call    cs:__imp_AddAccessAllowedAceEx
0x1800d458e  test    eax, eax
0x1800d4590  jnz     short loc_1800D45A7
0x1800d4592  call    cs:__imp_GetLastError
0x1800d4598  mov     esi, eax
0x1800d459a  test    eax, eax
0x1800d459c  jle     short loc_1800D45A7
0x1800d459e  movzx   esi, ax
0x1800d45a1  or      esi, 80070000h
0x1800d45a7  mov     eax, esi
0x1800d45a9  add     rsp, 38h
0x1800d45ad  pop     r15
0x1800d45af  pop     r14
0x1800d45b1  pop     rdi
0x1800d45b2  pop     rsi
0x1800d45b3  pop     rbp
0x1800d45b4  pop     rbx
0x1800d45b5  retn
```

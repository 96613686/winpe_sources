# HasActiveLocalAdminAccount

- ea: `0x1400123f4`
- end: `0x1400125d6`
- name: `HasActiveLocalAdminAccount`
- size: `482`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400045a8`
- `0x140004600`
- `0x140011f20`
- `0x1400123f4`

## import_xrefs

- `samcli!NetLocalGroupGetMembers` at `0x1400124e4`
- `samcli!NetLocalGroupGetMembers` at `0x1400124e4`
- `samcli!NetUserGetInfo` at `0x140012528`
- `samcli!NetUserGetInfo` at `0x140012528`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x140012424`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x140012424`
- `netutils!NetApiBufferFree` at `0x14001254d`
- `netutils!NetApiBufferFree` at `0x14001255e`
- `netutils!NetApiBufferFree` at `0x1400125a2`
- `netutils!NetApiBufferFree` at `0x1400125aa`
- `netutils!NetApiBufferFree` at `0x1400125b4`
- `netutils!NetApiBufferFree` at `0x14001254d`
- `netutils!NetApiBufferFree` at `0x14001255e`
- `netutils!NetApiBufferFree` at `0x1400125a2`
- `netutils!NetApiBufferFree` at `0x1400125aa`
- `netutils!NetApiBufferFree` at `0x1400125b4`

## pseudocode

```c
char HasActiveLocalAdminAccount()
{
  DWORD v0; // ecx
  unsigned __int64 v1; // rcx
  unsigned __int64 v2; // rcx
  unsigned int v3; // ebx
  WCHAR *v4; // rcx
  DWORD Members; // eax
  DWORD v6; // edi
  int v7; // ebx
  WCHAR *v8; // rcx
  WCHAR *v10; // rcx
  LPCWSTR localgroupname; // [rsp+40h] [rbp-49h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-41h] BYREF
  DWORD entriesread; // [rsp+4Ch] [rbp-3Dh] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-39h] BYREF
  DWORD totalentries; // [rsp+58h] [rbp-31h] BYREF
  LPBYTE v16; // [rsp+60h] [rbp-29h] BYREF
  LPCWSTR *p_localgroupname; // [rsp+68h] [rbp-21h]
  const WCHAR *v18; // [rsp+70h] [rbp-19h] BYREF
  char v19; // [rsp+78h] [rbp-11h]
  ULONG_PTR resumehandle; // [rsp+80h] [rbp-9h] BYREF
  WCHAR Buffer[20]; // [rsp+88h] [rbp-1h] BYREF

  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return 0;
  v0 = nSize;
  Buffer[nSize] = 92;
  v1 = v0 + 1;
  nSize = v1;
  v2 = v1;
  if ( v2 >= 17 )
    _report_rangecheckfailure();
  Buffer[v2] = 0;
  p_localgroupname = &localgroupname;
  localgroupname = 0;
  v18 = 0;
  v19 = 1;
  v3 = (unsigned int)GetUserNameForLocalAdministrators(&v18) >> 31;
  if ( v19 )
  {
    v4 = (WCHAR *)*p_localgroupname;
    *p_localgroupname = v18;
    if ( v4 )
      operator delete(v4);
  }
  if ( (_BYTE)v3 )
  {
LABEL_16:
    v8 = (WCHAR *)localgroupname;
    localgroupname = 0;
    if ( v8 )
      operator delete(v8);
    return 0;
  }
  while ( 1 )
  {
    bufptr = 0;
    resumehandle = 0;
    totalentries = 0;
    entriesread = 0;
    Members = NetLocalGroupGetMembers(
                0,
                localgroupname,
                2u,
                &bufptr,
                0xFFFFFFFF,
                &entriesread,
                &totalentries,
                &resumehandle);
    v6 = Members;
    if ( Members && Members != 234 )
    {
      NetApiBufferFree(bufptr);
      goto LABEL_16;
    }
    v7 = 0;
    if ( entriesread )
      break;
LABEL_15:
    NetApiBufferFree(bufptr);
    if ( v6 != 234 )
      goto LABEL_16;
  }
  while ( 1 )
  {
    v16 = 0;
    if ( !NetUserGetInfo(0, (LPCWSTR)(*(_QWORD *)&bufptr[24 * v7 + 16] + 2LL * nSize), 1u, &v16)
      && *(_DWORD *)&bufptr[24 * v7 + 8] == 1
      && (v16[20] & 2) != 0
      && (v16[40] & 2) == 0 )
    {
      break;
    }
    NetApiBufferFree(v16);
    if ( ++v7 >= entriesread )
      goto LABEL_15;
  }
  NetApiBufferFree(v16);
  NetApiBufferFree(bufptr);
  v10 = (WCHAR *)localgroupname;
  localgroupname = 0;
  if ( v10 )
    operator delete(v10);
  return 1;
}

```

## disassembly

```asm
0x1400123f4  push    rbp
0x1400123f6  push    rbx
0x1400123f7  push    rsi
0x1400123f8  push    rdi
0x1400123f9  push    r14
0x1400123fb  lea     rbp, [rsp-37h]
0x140012400  sub     rsp, 0C0h
0x140012407  mov     rax, cs:__security_cookie
0x14001240e  xor     rax, rsp
0x140012411  mov     [rbp+57h+var_30], rax
0x140012415  lea     rdx, [rbp+57h+nSize]; nSize
0x140012419  mov     [rbp+57h+nSize], 10h
0x140012420  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x140012424  call    cs:__imp_GetComputerNameW
0x14001242a  xor     r14d, r14d
0x14001242d  test    eax, eax
0x14001242f  jz      loc_140012582
0x140012435  mov     ecx, [rbp+57h+nSize]
0x140012438  lea     edx, [r14+5Ch]
0x14001243c  mov     [rbp+rcx*2+57h+Buffer], dx
0x140012441  inc     ecx
0x140012443  mov     [rbp+57h+nSize], ecx
0x140012446  add     rcx, rcx
0x140012449  cmp     rcx, 22h ; '"'
0x14001244d  jnb     loc_1400125D0
0x140012453  mov     [rbp+rcx+57h+Buffer], r14w
0x140012459  lea     rax, [rbp+57h+localgroupname]
0x14001245d  lea     rcx, [rbp+57h+var_70]
0x140012461  mov     [rbp+57h+var_78], rax
0x140012465  mov     [rbp+57h+localgroupname], r14
0x140012469  mov     [rbp+57h+var_70], r14
0x14001246d  mov     [rbp+57h+var_68], 1
0x140012471  call    GetUserNameForLocalAdministrators
0x140012476  mov     ebx, eax
0x140012478  shr     ebx, 1Fh
0x14001247b  cmp     [rbp+57h+var_68], r14b
0x14001247f  jz      short loc_140012499
0x140012481  mov     r8, [rbp+57h+var_78]
0x140012485  mov     rdx, [rbp+57h+var_70]
0x140012489  mov     rcx, [r8]; Block
0x14001248c  mov     [r8], rdx
0x14001248f  test    rcx, rcx
0x140012492  jz      short loc_140012499
0x140012494  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012499  test    bl, bl
0x14001249b  jnz     loc_140012570
0x1400124a1  mov     rdx, [rbp+57h+localgroupname]; localgroupname
0x1400124a5  lea     rax, [rbp+57h+var_60]
0x1400124a9  mov     [rsp+0E0h+resumehandle], rax; resumehandle
0x1400124ae  lea     r9, [rbp+57h+bufptr]; bufptr
0x1400124b2  lea     rax, [rbp+57h+var_88]
0x1400124b6  mov     [rbp+57h+bufptr], r14
0x1400124ba  mov     [rsp+0E0h+totalentries], rax; totalentries
0x1400124bf  mov     r8d, 2; level
0x1400124c5  lea     rax, [rbp+57h+var_94]
0x1400124c9  mov     [rbp+57h+var_60], r14
0x1400124cd  mov     [rsp+0E0h+entriesread], rax; entriesread
0x1400124d2  xor     ecx, ecx; servername
0x1400124d4  mov     [rsp+0E0h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x1400124dc  mov     [rbp+57h+var_88], r14d
0x1400124e0  mov     [rbp+57h+var_94], r14d
0x1400124e4  call    cs:__imp_NetLocalGroupGetMembers
0x1400124ea  mov     edi, eax
0x1400124ec  test    eax, eax
0x1400124ee  jz      short loc_1400124FB
0x1400124f0  cmp     eax, 0EAh
0x1400124f5  jnz     loc_14001259E
0x1400124fb  mov     ebx, r14d
0x1400124fe  cmp     [rbp+57h+var_94], r14d
0x140012502  jbe     short loc_14001255A
0x140012504  mov     rax, [rbp+57h+bufptr]
0x140012508  lea     r9, [rbp+57h+var_80]; bufptr
0x14001250c  mov     edx, [rbp+57h+nSize]
0x14001250f  mov     ecx, ebx
0x140012511  mov     [rbp+57h+var_80], r14
0x140012515  lea     rsi, [rcx+rcx*2]
0x140012519  mov     rcx, [rax+rsi*8+10h]
0x14001251e  lea     rdx, [rcx+rdx*2]; username
0x140012522  xor     ecx, ecx; servername
0x140012524  lea     r8d, [rcx+1]; level
0x140012528  call    cs:__imp_NetUserGetInfo
0x14001252e  mov     rcx, [rbp+57h+var_80]; Buffer
0x140012532  test    eax, eax
0x140012534  jnz     short loc_14001254D
0x140012536  mov     rax, [rbp+57h+bufptr]
0x14001253a  cmp     dword ptr [rax+rsi*8+8], 1
0x14001253f  jnz     short loc_14001254D
0x140012541  test    byte ptr [rcx+14h], 2
0x140012545  jz      short loc_14001254D
0x140012547  test    byte ptr [rcx+28h], 2
0x14001254b  jz      short loc_1400125AA
0x14001254d  call    cs:__imp_NetApiBufferFree
0x140012553  inc     ebx
0x140012555  cmp     ebx, [rbp+57h+var_94]
0x140012558  jb      short loc_140012504
0x14001255a  mov     rcx, [rbp+57h+bufptr]; Buffer
0x14001255e  call    cs:__imp_NetApiBufferFree
0x140012564  cmp     edi, 0EAh
0x14001256a  jz      loc_1400124A1
0x140012570  mov     rcx, [rbp+57h+localgroupname]; Block
0x140012574  mov     [rbp+57h+localgroupname], r14
0x140012578  test    rcx, rcx
0x14001257b  jz      short loc_140012582
0x14001257d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012582  xor     al, al
0x140012584  mov     rcx, [rbp+57h+var_30]
0x140012588  xor     rcx, rsp; StackCookie
0x14001258b  call    __security_check_cookie
0x140012590  add     rsp, 0C0h
0x140012597  pop     r14
0x140012599  pop     rdi
0x14001259a  pop     rsi
0x14001259b  pop     rbx
0x14001259c  pop     rbp
0x14001259d  retn
0x14001259e  mov     rcx, [rbp+57h+bufptr]; Buffer
0x1400125a2  call    cs:__imp_NetApiBufferFree
0x1400125a8  jmp     short loc_140012570
0x1400125aa  call    cs:__imp_NetApiBufferFree
0x1400125b0  mov     rcx, [rbp+57h+bufptr]; Buffer
0x1400125b4  call    cs:__imp_NetApiBufferFree
0x1400125ba  mov     rcx, [rbp+57h+localgroupname]; Block
0x1400125be  mov     [rbp+57h+localgroupname], r14
0x1400125c2  test    rcx, rcx
0x1400125c5  jz      short loc_1400125CC
0x1400125c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400125cc  mov     al, 1
0x1400125ce  jmp     short loc_140012584
0x1400125d0  call    __report_rangecheckfailure
```

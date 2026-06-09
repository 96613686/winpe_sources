# sub_1800DCFC4

- ea: `0x1800dcfc4`
- end: `0x1800dd1ee`
- name: `sub_1800DCFC4`
- size: `554`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18007b9fc`
- `0x18007cd00`
- `0x1800a5c80`
- `0x1800b2160`
- `0x1800bfb60`
- `0x1800c0870`
- `0x1800d8734`

## callees

- `0x18001b270`
- `0x18003b830`
- `0x1800733a8`
- `0x1800dcfc4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800dd027`
- `KERNEL32!LocalFree` at `0x1800dd16e`
- `KERNEL32!LocalFree` at `0x1800dd027`
- `KERNEL32!LocalFree` at `0x1800dd16e`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800dd050`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800dd050`
- `ADVAPI32!CheckTokenMembership` at `0x1800dd0fe`
- `ADVAPI32!CheckTokenMembership` at `0x1800dd0fe`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800dd0e2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800dd0e2`

## pseudocode

```c
__int64 __fastcall sub_1800DCFC4(__int64 a1, int a2, WINBOOL *a3)
{
  int v5; // ebx
  unsigned __int64 v7; // rdi
  const WCHAR *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  HLOCAL hMem; // [rsp+60h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+6Ch] [rbp-14h] BYREF

  IsMember = 0;
  hMem = 0;
  v5 = 0;
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v7 = 0;
  while ( 1 )
  {
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( (a2 & qword_18019E000[v7]) == 0 )
      goto LABEL_22;
    v8 = (const WCHAR *)qword_18019E000[v7 + 1];
    if ( v8 )
    {
      if ( !ConvertStringSidToSidW(v8, &hMem) )
      {
        v9 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 11, qword_18014B400, v9);
        v5 = 0;
        goto LABEL_22;
      }
      goto LABEL_15;
    }
    if ( LODWORD(qword_18019E000[v7]) != 1 )
      goto LABEL_22;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &hMem) )
      break;
LABEL_15:
    IsMember = 0;
    if ( CheckTokenMembership(0, hMem, &IsMember) )
    {
      v5 = 0;
    }
    else
    {
      v10 = sub_18001B270();
      v5 = v10;
      v11 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      {
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 10, qword_18014B400, v10);
        v11 = off_18019DE80;
      }
      if ( v5 < 0 )
      {
        if ( v11 != &off_18019DE80 && (*((_BYTE *)v11 + 28) & 1) != 0 )
        {
          v12 = 13;
          v13 = (unsigned int)v5;
LABEL_34:
          sub_1800733A8(v11[2], v12, qword_18014B400, v13);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
    }
    if ( IsMember )
    {
      v5 = 0;
LABEL_23:
      *a3 = IsMember;
      goto LABEL_24;
    }
LABEL_22:
    v7 += 2LL;
    if ( v7 >= 20 )
      goto LABEL_23;
  }
  v14 = sub_18001B270();
  v5 = v14;
  v11 = off_18019DE80;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
  {
    v12 = 12;
    v13 = v14;
    goto LABEL_34;
  }
LABEL_24:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800dcfc4  mov     [rsp-28h+arg_0], rbx
0x1800dcfc9  mov     [rsp-28h+arg_8], rsi
0x1800dcfce  push    rbp
0x1800dcfcf  push    rdi
0x1800dcfd0  push    r12
0x1800dcfd2  push    r14
0x1800dcfd4  push    r15
0x1800dcfd6  mov     rbp, rsp
0x1800dcfd9  sub     rsp, 80h
0x1800dcfe0  mov     rax, cs:__security_cookie
0x1800dcfe7  xor     rax, rsp
0x1800dcfea  mov     [rbp+var_8], rax
0x1800dcfee  xor     r15d, r15d
0x1800dcff1  mov     rsi, r8
0x1800dcff4  mov     [rbp+IsMember], r15d
0x1800dcff8  mov     r14d, edx
0x1800dcffb  mov     [rbp+hMem], r15
0x1800dcfff  mov     ebx, r15d
0x1800dd002  test    r8, r8
0x1800dd005  jnz     short loc_1800DD011
0x1800dd007  mov     eax, 80070057h
0x1800dd00c  jmp     loc_1800DD176
0x1800dd011  mov     [r8], r15d
0x1800dd014  lea     r12, off_18019DE80
0x1800dd01b  mov     rdi, r15
0x1800dd01e  mov     rcx, [rbp+hMem]; hMem
0x1800dd022  test    rcx, rcx
0x1800dd025  jz      short loc_1800DD031
0x1800dd027  call    cs:__imp_LocalFree
0x1800dd02d  mov     [rbp+hMem], r15
0x1800dd031  lea     rax, qword_18019E000
0x1800dd038  test    [rdi+rax], r14d
0x1800dd03c  jz      loc_1800DD14F
0x1800dd042  mov     rcx, [rdi+rax+8]; StringSid
0x1800dd047  test    rcx, rcx
0x1800dd04a  jz      short loc_1800DD095
0x1800dd04c  lea     rdx, [rbp+hMem]; Sid
0x1800dd050  call    cs:__imp_ConvertStringSidToSidW
0x1800dd056  test    eax, eax
0x1800dd058  jnz     loc_1800DD0F0
0x1800dd05e  call    sub_18001B270
0x1800dd063  mov     rcx, cs:off_18019DE80
0x1800dd06a  cmp     rcx, r12
0x1800dd06d  jz      short loc_1800DD08D
0x1800dd06f  test    byte ptr [rcx+1Ch], 1
0x1800dd073  jz      short loc_1800DD08D
0x1800dd075  mov     rcx, [rcx+10h]
0x1800dd079  lea     r8, qword_18014B400
0x1800dd080  mov     edx, 0Bh
0x1800dd085  mov     r9d, eax
0x1800dd088  call    sub_1800733A8
0x1800dd08d  mov     ebx, r15d
0x1800dd090  jmp     loc_1800DD14F
0x1800dd095  cmp     dword ptr [rdi+rax], 1
0x1800dd099  jnz     loc_1800DD14F
0x1800dd09f  lea     rax, [rbp+hMem]
0x1800dd0a3  mov     dword ptr [rbp+pIdentifierAuthority.Value], r15d
0x1800dd0a7  mov     [rsp+80h+pSid], rax; pSid
0x1800dd0ac  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800dd0b0  mov     [rsp+80h+nSubAuthority7], r15d; nSubAuthority7
0x1800dd0b5  mov     r9d, 220h; nSubAuthority1
0x1800dd0bb  mov     [rsp+80h+nSubAuthority6], r15d; nSubAuthority6
0x1800dd0c0  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800dd0c6  mov     [rsp+80h+nSubAuthority5], r15d; nSubAuthority5
0x1800dd0cb  mov     dl, 2; nSubAuthorityCount
0x1800dd0cd  mov     [rsp+80h+nSubAuthority4], r15d; nSubAuthority4
0x1800dd0d2  mov     [rsp+80h+nSubAuthority3], r15d; nSubAuthority3
0x1800dd0d7  mov     [rsp+80h+nSubAuthority2], r15d; nSubAuthority2
0x1800dd0dc  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800dd0e2  call    cs:AllocateAndInitializeSid
0x1800dd0e8  test    eax, eax
0x1800dd0ea  jz      loc_1800DD1B8
0x1800dd0f0  mov     rdx, [rbp+hMem]; SidToCheck
0x1800dd0f4  lea     r8, [rbp+IsMember]; IsMember
0x1800dd0f8  xor     ecx, ecx; TokenHandle
0x1800dd0fa  mov     [rbp+IsMember], r15d
0x1800dd0fe  call    cs:CheckTokenMembership
0x1800dd104  test    eax, eax
0x1800dd106  jz      short loc_1800DD10D
0x1800dd108  mov     ebx, r15d
0x1800dd10b  jmp     short loc_1800DD149
0x1800dd10d  call    sub_18001B270
0x1800dd112  mov     ebx, eax
0x1800dd114  mov     rcx, cs:off_18019DE80
0x1800dd11b  cmp     rcx, r12
0x1800dd11e  jz      short loc_1800DD145
0x1800dd120  test    byte ptr [rcx+1Ch], 1
0x1800dd124  jz      short loc_1800DD145
0x1800dd126  mov     rcx, [rcx+10h]
0x1800dd12a  lea     r8, qword_18014B400
0x1800dd131  mov     edx, 0Ah
0x1800dd136  mov     r9d, eax
0x1800dd139  call    sub_1800733A8
0x1800dd13e  mov     rcx, cs:off_18019DE80
0x1800dd145  test    ebx, ebx
0x1800dd147  js      short loc_1800DD1A3
0x1800dd149  cmp     [rbp+IsMember], r15d
0x1800dd14d  jnz     short loc_1800DD19E
0x1800dd14f  add     rdi, 10h
0x1800dd153  cmp     rdi, 0A0h
0x1800dd15a  jb      loc_1800DD01E
0x1800dd160  mov     eax, [rbp+IsMember]
0x1800dd163  mov     [rsi], eax
0x1800dd165  mov     rcx, [rbp+hMem]; hMem
0x1800dd169  test    rcx, rcx
0x1800dd16c  jz      short loc_1800DD174
0x1800dd16e  call    cs:__imp_LocalFree
0x1800dd174  mov     eax, ebx
0x1800dd176  mov     rcx, [rbp+var_8]
0x1800dd17a  xor     rcx, rsp; StackCookie
0x1800dd17d  call    __security_check_cookie
0x1800dd182  lea     r11, [rsp+80h+var_s0]
0x1800dd18a  mov     rbx, [r11+30h]
0x1800dd18e  mov     rsi, [r11+38h]
0x1800dd192  mov     rsp, r11
0x1800dd195  pop     r15
0x1800dd197  pop     r14
0x1800dd199  pop     r12
0x1800dd19b  pop     rdi
0x1800dd19c  pop     rbp
0x1800dd19d  retn
0x1800dd19e  mov     ebx, r15d
0x1800dd1a1  jmp     short loc_1800DD160
0x1800dd1a3  cmp     rcx, r12
0x1800dd1a6  jz      short loc_1800DD165
0x1800dd1a8  test    byte ptr [rcx+1Ch], 1
0x1800dd1ac  jz      short loc_1800DD165
0x1800dd1ae  mov     edx, 0Dh
0x1800dd1b3  mov     r9d, ebx
0x1800dd1b6  jmp     short loc_1800DD1D9
0x1800dd1b8  call    sub_18001B270
0x1800dd1bd  mov     ebx, eax
0x1800dd1bf  mov     rcx, cs:off_18019DE80
0x1800dd1c6  cmp     rcx, r12
0x1800dd1c9  jz      short loc_1800DD165
0x1800dd1cb  test    byte ptr [rcx+1Ch], 1
0x1800dd1cf  jz      short loc_1800DD165
0x1800dd1d1  mov     edx, 0Ch
0x1800dd1d6  mov     r9d, eax
0x1800dd1d9  mov     rcx, [rcx+10h]
0x1800dd1dd  lea     r8, qword_18014B400
0x1800dd1e4  call    sub_1800733A8
0x1800dd1e9  jmp     loc_1800DD165
```

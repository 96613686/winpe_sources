# RegEnumAccountsCB

- ea: `0x14000e640`
- end: `0x14000e837`
- name: `RegEnumAccountsCB`
- size: `503`
- prototype: `__int64 __fastcall(HKEY, LPCWSTR StringSid)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1400023ec`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14000ce98`
- `0x14000dd74`
- `0x14000e640`
- `0x14008b010`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000e6a2`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000e6a2`
- `KERNEL32!GetLastError` at `0x14000e6d6`
- `KERNEL32!GetLastError` at `0x14000e6d6`
- `KERNEL32!LocalFree` at `0x14000e7fe`
- `KERNEL32!LocalFree` at `0x14000e7fe`

## pseudocode

```c
__int64 __fastcall RegEnumAccountsCB(HKEY a1, LPCWSTR StringSid)
{
  char LastError; // al
  struct CFaxAccount *v5; // rax
  struct CFaxAccount *v6; // rbx
  unsigned int v7; // eax
  CFaxAccountList *v8; // rcx
  int v9; // edi
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  PSID Sid; // [rsp+78h] [rbp+10h] BYREF

  Sid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  if ( StringSid )
  {
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          (_DWORD)StringSid,
          LastError);
      }
      return 1;
    }
    v5 = (struct CFaxAccount *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( !v5 )
    {
      v6 = 0;
      v9 = 8;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
      }
      goto LABEL_27;
    }
    *((_QWORD *)v5 + 1) = 0;
    *(_QWORD *)v5 = &CFaxAccount::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 6) = 0;
    v7 = CFaxAccount::Load(v5, a1, Sid);
    v9 = v7;
    if ( v7 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v11 = 79;
    }
    else
    {
      v7 = CFaxAccountList::AddAccount(v8, v6, 0);
      v9 = v7;
      if ( !v7 )
        goto LABEL_27;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v11 = 80;
    }
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v7);
LABEL_27:
    if ( Sid )
      LocalFree(Sid);
    if ( v9 && v6 )
      (**(void (__fastcall ***)(struct CFaxAccount *, __int64))v6)(v6, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x14000e640  push    rbx
0x14000e642  push    rdi
0x14000e643  push    r14
0x14000e645  push    r15
0x14000e647  sub     rsp, 48h
0x14000e64b  mov     rbx, rdx
0x14000e64e  mov     [rsp+68h+Sid], 0
0x14000e657  mov     rdi, rcx
0x14000e65a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e661  lea     r14, WPP_GLOBAL_Control
0x14000e668  lea     r15, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e66f  cmp     rcx, r14
0x14000e672  jz      short loc_14000E691
0x14000e674  test    byte ptr [rcx+1Ch], 4
0x14000e678  jz      short loc_14000E691
0x14000e67a  cmp     byte ptr [rcx+19h], 5
0x14000e67e  jb      short loc_14000E691
0x14000e680  mov     rcx, [rcx+10h]
0x14000e684  mov     edx, 4Ch ; 'L'
0x14000e689  mov     r8, r15
0x14000e68c  call    WPP_SF_
0x14000e691  test    rbx, rbx
0x14000e694  jz      loc_14000E826
0x14000e69a  lea     rdx, [rsp+68h+Sid]; Sid
0x14000e69f  mov     rcx, rbx; StringSid
0x14000e6a2  call    cs:__imp_ConvertStringSidToSidW
0x14000e6a9  nop     dword ptr [rax+rax+00h]
0x14000e6ae  test    eax, eax
0x14000e6b0  jnz     short loc_14000E706
0x14000e6b2  mov     rax, cs:WPP_GLOBAL_Control
0x14000e6b9  cmp     rax, r14
0x14000e6bc  jz      loc_14000E826
0x14000e6c2  test    byte ptr [rax+1Ch], 4
0x14000e6c6  jz      loc_14000E826
0x14000e6cc  cmp     byte ptr [rax+19h], 2
0x14000e6d0  jb      loc_14000E826
0x14000e6d6  call    cs:__imp_GetLastError
0x14000e6dd  nop     dword ptr [rax+rax+00h]
0x14000e6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6e9  mov     edx, 4Dh ; 'M'
0x14000e6ee  mov     r9, rbx
0x14000e6f1  mov     [rsp+68h+var_48], eax
0x14000e6f5  mov     r8, r15
0x14000e6f8  mov     rcx, [rcx+10h]
0x14000e6fc  call    WPP_SF_Sd
0x14000e701  jmp     loc_14000E826
0x14000e706  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e70d  mov     ecx, 20h ; ' '; unsigned __int64
0x14000e712  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000e717  mov     [rsp+68h+var_38], rax
0x14000e71c  mov     rbx, rax
0x14000e71f  test    rax, rax
0x14000e722  jz      loc_14000E7C6
0x14000e728  mov     qword ptr [rbx+8], 0
0x14000e730  lea     rax, ??_7CFaxAccount@@6B@; const CFaxAccount::`vftable'
0x14000e737  mov     [rbx], rax
0x14000e73a  mov     qword ptr [rbx+10h], 0
0x14000e742  mov     dword ptr [rbx+18h], 0
0x14000e749  test    rbx, rbx
0x14000e74c  jz      short loc_14000E7C8
0x14000e74e  mov     r8, [rsp+68h+Sid]; void *
0x14000e753  mov     rdx, rdi; HKEY
0x14000e756  mov     rcx, rbx; this
0x14000e759  call    ?Load@CFaxAccount@@QEAAKPEAUHKEY__@@PEAX@Z; CFaxAccount::Load(HKEY__ *,void *)
0x14000e75e  mov     edi, eax
0x14000e760  test    eax, eax
0x14000e762  jz      short loc_14000E796
0x14000e764  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e76b  cmp     rcx, r14
0x14000e76e  jz      loc_14000E7F4
0x14000e774  test    byte ptr [rcx+1Ch], 4
0x14000e778  jz      short loc_14000E7F4
0x14000e77a  cmp     byte ptr [rcx+19h], 2
0x14000e77e  jb      short loc_14000E7F4
0x14000e780  mov     edx, 4Fh ; 'O'
0x14000e785  mov     rcx, [rcx+10h]
0x14000e789  mov     r9d, eax
0x14000e78c  mov     r8, r15
0x14000e78f  call    WPP_SF_d
0x14000e794  jmp     short loc_14000E7F4
0x14000e796  xor     r8d, r8d; int
0x14000e799  mov     rdx, rbx; struct CFaxAccount *
0x14000e79c  call    ?AddAccount@CFaxAccountList@@QEAAKAEAVCFaxAccount@@H@Z; CFaxAccountList::AddAccount(CFaxAccount &,int)
0x14000e7a1  mov     edi, eax
0x14000e7a3  test    eax, eax
0x14000e7a5  jz      short loc_14000E7F4
0x14000e7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7ae  cmp     rcx, r14
0x14000e7b1  jz      short loc_14000E7F4
0x14000e7b3  test    byte ptr [rcx+1Ch], 4
0x14000e7b7  jz      short loc_14000E7F4
0x14000e7b9  cmp     byte ptr [rcx+19h], 2
0x14000e7bd  jb      short loc_14000E7F4
0x14000e7bf  mov     edx, 50h ; 'P'
0x14000e7c4  jmp     short loc_14000E785
0x14000e7c6  xor     ebx, ebx
0x14000e7c8  mov     edi, 8
0x14000e7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7d4  cmp     rcx, r14
0x14000e7d7  jz      short loc_14000E7F4
0x14000e7d9  test    byte ptr [rcx+1Ch], 4
0x14000e7dd  jz      short loc_14000E7F4
0x14000e7df  cmp     byte ptr [rcx+19h], 2
0x14000e7e3  jb      short loc_14000E7F4
0x14000e7e5  mov     rcx, [rcx+10h]
0x14000e7e9  lea     edx, [rdi+46h]
0x14000e7ec  mov     r8, r15
0x14000e7ef  call    WPP_SF_
0x14000e7f4  mov     rcx, [rsp+68h+Sid]; hMem
0x14000e7f9  test    rcx, rcx
0x14000e7fc  jz      short loc_14000E80A
0x14000e7fe  call    cs:__imp_LocalFree
0x14000e805  nop     dword ptr [rax+rax+00h]
0x14000e80a  test    edi, edi
0x14000e80c  jz      short loc_14000E826
0x14000e80e  test    rbx, rbx
0x14000e811  jz      short loc_14000E826
0x14000e813  mov     rdx, [rbx]
0x14000e816  mov     rcx, rbx
0x14000e819  mov     rax, [rdx]
0x14000e81c  mov     edx, 1
0x14000e821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e826  mov     eax, 1
0x14000e82b  add     rsp, 48h
0x14000e82f  pop     r15
0x14000e831  pop     r14
0x14000e833  pop     rdi
0x14000e834  pop     rbx
0x14000e835  retn
```

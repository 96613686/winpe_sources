# RegEnumAccountsCB

- ea: `0x14000df00`
- end: `0x14000e0e4`
- name: `RegEnumAccountsCB`
- size: `484`
- prototype: `__int64 __fastcall(HKEY, LPCWSTR StringSid)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1400023cc`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14000c7e8`
- `0x14000d680`
- `0x14000df00`
- `0x140085010`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000df62`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000df62`
- `KERNEL32!GetLastError` at `0x14000df90`
- `KERNEL32!GetLastError` at `0x14000df90`
- `KERNEL32!LocalFree` at `0x14000e0b2`
- `KERNEL32!LocalFree` at `0x14000e0b2`

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
0x14000df00  push    rbx
0x14000df02  push    rdi
0x14000df03  push    r14
0x14000df05  push    r15
0x14000df07  sub     rsp, 48h
0x14000df0b  mov     rbx, rdx
0x14000df0e  mov     [rsp+68h+Sid], 0
0x14000df17  mov     rdi, rcx
0x14000df1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df21  lea     r14, WPP_GLOBAL_Control
0x14000df28  lea     r15, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000df2f  cmp     rcx, r14
0x14000df32  jz      short loc_14000DF51
0x14000df34  test    byte ptr [rcx+1Ch], 4
0x14000df38  jz      short loc_14000DF51
0x14000df3a  cmp     byte ptr [rcx+19h], 5
0x14000df3e  jb      short loc_14000DF51
0x14000df40  mov     rcx, [rcx+10h]
0x14000df44  mov     edx, 4Ch ; 'L'
0x14000df49  mov     r8, r15
0x14000df4c  call    WPP_SF_
0x14000df51  test    rbx, rbx
0x14000df54  jz      loc_14000E0D4
0x14000df5a  lea     rdx, [rsp+68h+Sid]; Sid
0x14000df5f  mov     rcx, rbx; StringSid
0x14000df62  call    cs:__imp_ConvertStringSidToSidW
0x14000df68  test    eax, eax
0x14000df6a  jnz     short loc_14000DFBA
0x14000df6c  mov     rax, cs:WPP_GLOBAL_Control
0x14000df73  cmp     rax, r14
0x14000df76  jz      loc_14000E0D4
0x14000df7c  test    byte ptr [rax+1Ch], 4
0x14000df80  jz      loc_14000E0D4
0x14000df86  cmp     byte ptr [rax+19h], 2
0x14000df8a  jb      loc_14000E0D4
0x14000df90  call    cs:__imp_GetLastError
0x14000df96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df9d  mov     edx, 4Dh ; 'M'
0x14000dfa2  mov     r9, rbx
0x14000dfa5  mov     [rsp+68h+var_48], eax
0x14000dfa9  mov     r8, r15
0x14000dfac  mov     rcx, [rcx+10h]
0x14000dfb0  call    WPP_SF_Sd
0x14000dfb5  jmp     loc_14000E0D4
0x14000dfba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dfc1  mov     ecx, 20h ; ' '; unsigned __int64
0x14000dfc6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000dfcb  mov     [rsp+68h+var_38], rax
0x14000dfd0  mov     rbx, rax
0x14000dfd3  test    rax, rax
0x14000dfd6  jz      loc_14000E07A
0x14000dfdc  mov     qword ptr [rbx+8], 0
0x14000dfe4  lea     rax, ??_7CFaxAccount@@6B@; const CFaxAccount::`vftable'
0x14000dfeb  mov     [rbx], rax
0x14000dfee  mov     qword ptr [rbx+10h], 0
0x14000dff6  mov     dword ptr [rbx+18h], 0
0x14000dffd  test    rbx, rbx
0x14000e000  jz      short loc_14000E07C
0x14000e002  mov     r8, [rsp+68h+Sid]; void *
0x14000e007  mov     rdx, rdi; HKEY
0x14000e00a  mov     rcx, rbx; this
0x14000e00d  call    ?Load@CFaxAccount@@QEAAKPEAUHKEY__@@PEAX@Z; CFaxAccount::Load(HKEY__ *,void *)
0x14000e012  mov     edi, eax
0x14000e014  test    eax, eax
0x14000e016  jz      short loc_14000E04A
0x14000e018  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e01f  cmp     rcx, r14
0x14000e022  jz      loc_14000E0A8
0x14000e028  test    byte ptr [rcx+1Ch], 4
0x14000e02c  jz      short loc_14000E0A8
0x14000e02e  cmp     byte ptr [rcx+19h], 2
0x14000e032  jb      short loc_14000E0A8
0x14000e034  mov     edx, 4Fh ; 'O'
0x14000e039  mov     rcx, [rcx+10h]
0x14000e03d  mov     r9d, eax
0x14000e040  mov     r8, r15
0x14000e043  call    WPP_SF_d
0x14000e048  jmp     short loc_14000E0A8
0x14000e04a  xor     r8d, r8d; int
0x14000e04d  mov     rdx, rbx; struct CFaxAccount *
0x14000e050  call    ?AddAccount@CFaxAccountList@@QEAAKAEAVCFaxAccount@@H@Z; CFaxAccountList::AddAccount(CFaxAccount &,int)
0x14000e055  mov     edi, eax
0x14000e057  test    eax, eax
0x14000e059  jz      short loc_14000E0A8
0x14000e05b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e062  cmp     rcx, r14
0x14000e065  jz      short loc_14000E0A8
0x14000e067  test    byte ptr [rcx+1Ch], 4
0x14000e06b  jz      short loc_14000E0A8
0x14000e06d  cmp     byte ptr [rcx+19h], 2
0x14000e071  jb      short loc_14000E0A8
0x14000e073  mov     edx, 50h ; 'P'
0x14000e078  jmp     short loc_14000E039
0x14000e07a  xor     ebx, ebx
0x14000e07c  mov     edi, 8
0x14000e081  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e088  cmp     rcx, r14
0x14000e08b  jz      short loc_14000E0A8
0x14000e08d  test    byte ptr [rcx+1Ch], 4
0x14000e091  jz      short loc_14000E0A8
0x14000e093  cmp     byte ptr [rcx+19h], 2
0x14000e097  jb      short loc_14000E0A8
0x14000e099  mov     rcx, [rcx+10h]
0x14000e09d  lea     edx, [rdi+46h]
0x14000e0a0  mov     r8, r15
0x14000e0a3  call    WPP_SF_
0x14000e0a8  mov     rcx, [rsp+68h+Sid]; hMem
0x14000e0ad  test    rcx, rcx
0x14000e0b0  jz      short loc_14000E0B8
0x14000e0b2  call    cs:__imp_LocalFree
0x14000e0b8  test    edi, edi
0x14000e0ba  jz      short loc_14000E0D4
0x14000e0bc  test    rbx, rbx
0x14000e0bf  jz      short loc_14000E0D4
0x14000e0c1  mov     rdx, [rbx]
0x14000e0c4  mov     rcx, rbx
0x14000e0c7  mov     rax, [rdx]
0x14000e0ca  mov     edx, 1
0x14000e0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0d4  mov     eax, 1
0x14000e0d9  add     rsp, 48h
0x14000e0dd  pop     r15
0x14000e0df  pop     r14
0x14000e0e1  pop     rdi
0x14000e0e2  pop     rbx
0x14000e0e3  retn
```

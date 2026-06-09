# RaInitSidList

- ea: `0x18000d590`
- end: `0x18000d74c`
- name: `RaInitSidList`
- size: `444`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x1800044a0`
- `0x18000d2d0`
- `0x18000d590`
- `0x18000d860`

## pseudocode

```c
__int64 __fastcall RaInitSidList(LPVOID *a1)
{
  unsigned int WellKnownSid; // ebx
  __int64 v3; // r8
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  WellKnownSid = RaCreateWellKnownSid(WinLocalSystemSid, a1);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 10;
LABEL_25:
    WPP_SF_D(v4[2], v5, v3, WellKnownSid);
LABEL_26:
    RaFreeSidList(a1);
    return WellKnownSid;
  }
  WellKnownSid = RaCreateWellKnownSid(WinLocalServiceSid, a1 + 1);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 11;
    goto LABEL_25;
  }
  WellKnownSid = RaCreateWellKnownSid(WinNetworkServiceSid, a1 + 2);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 12;
    goto LABEL_25;
  }
  WellKnownSid = RaCreateWellKnownSid(WinBuiltinGuestsSid, a1 + 3);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 13;
    goto LABEL_25;
  }
  WellKnownSid = RaCreateWellKnownSid(WinBuiltinAdministratorsSid, a1 + 4);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 14;
    goto LABEL_25;
  }
  WellKnownSid = RaCreateWellKnownSid(WinBuiltinNetworkConfigurationOperatorsSid, a1 + 5);
  if ( WellKnownSid )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v5 = 15;
    goto LABEL_25;
  }
  return WellKnownSid;
}

```

## disassembly

```asm
0x18000d590  push    rbx
0x18000d592  push    rbp
0x18000d593  push    rsi
0x18000d594  push    rdi
0x18000d595  push    r12
0x18000d597  push    r14
0x18000d599  push    r15
0x18000d59b  sub     rsp, 20h
0x18000d59f  mov     rdi, rcx
0x18000d5a2  mov     qword ptr [rcx], 0
0x18000d5a9  mov     qword ptr [rcx+8], 0
0x18000d5b1  mov     rdx, rcx
0x18000d5b4  mov     qword ptr [rcx+10h], 0
0x18000d5bc  mov     qword ptr [rcx+18h], 0
0x18000d5c4  mov     qword ptr [rcx+20h], 0
0x18000d5cc  mov     qword ptr [rcx+28h], 0
0x18000d5d4  mov     ecx, 16h; WellKnownSidType
0x18000d5d9  call    RaCreateWellKnownSid
0x18000d5de  mov     ebx, eax
0x18000d5e0  test    eax, eax
0x18000d5e2  jz      short loc_18000D60F
0x18000d5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5eb  lea     rax, WPP_GLOBAL_Control
0x18000d5f2  cmp     rcx, rax
0x18000d5f5  jz      loc_18000D733
0x18000d5fb  test    byte ptr [rcx+1Ch], 4
0x18000d5ff  jz      loc_18000D733
0x18000d605  mov     edx, 0Ah
0x18000d60a  jmp     loc_18000D727
0x18000d60f  lea     rdx, [rdi+8]
0x18000d613  mov     ecx, 17h; WellKnownSidType
0x18000d618  call    RaCreateWellKnownSid
0x18000d61d  mov     ebx, eax
0x18000d61f  test    eax, eax
0x18000d621  jz      short loc_18000D64E
0x18000d623  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d62a  lea     rax, WPP_GLOBAL_Control
0x18000d631  cmp     rcx, rax
0x18000d634  jz      loc_18000D733
0x18000d63a  test    byte ptr [rcx+1Ch], 4
0x18000d63e  jz      loc_18000D733
0x18000d644  mov     edx, 0Bh
0x18000d649  jmp     loc_18000D727
0x18000d64e  lea     rdx, [rdi+10h]
0x18000d652  mov     ecx, 18h; WellKnownSidType
0x18000d657  call    RaCreateWellKnownSid
0x18000d65c  mov     ebx, eax
0x18000d65e  test    eax, eax
0x18000d660  jz      short loc_18000D68D
0x18000d662  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d669  lea     rax, WPP_GLOBAL_Control
0x18000d670  cmp     rcx, rax
0x18000d673  jz      loc_18000D733
0x18000d679  test    byte ptr [rcx+1Ch], 4
0x18000d67d  jz      loc_18000D733
0x18000d683  mov     edx, 0Ch
0x18000d688  jmp     loc_18000D727
0x18000d68d  lea     rdx, [rdi+18h]
0x18000d691  mov     ecx, 1Ch; WellKnownSidType
0x18000d696  call    RaCreateWellKnownSid
0x18000d69b  mov     ebx, eax
0x18000d69d  test    eax, eax
0x18000d69f  jz      short loc_18000D6C1
0x18000d6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6a8  lea     rax, WPP_GLOBAL_Control
0x18000d6af  cmp     rcx, rax
0x18000d6b2  jz      short loc_18000D733
0x18000d6b4  test    byte ptr [rcx+1Ch], 4
0x18000d6b8  jz      short loc_18000D733
0x18000d6ba  mov     edx, 0Dh
0x18000d6bf  jmp     short loc_18000D727
0x18000d6c1  lea     rdx, [rdi+20h]
0x18000d6c5  mov     ecx, 1Ah; WellKnownSidType
0x18000d6ca  call    RaCreateWellKnownSid
0x18000d6cf  mov     ebx, eax
0x18000d6d1  test    eax, eax
0x18000d6d3  jz      short loc_18000D6F5
0x18000d6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6dc  lea     rax, WPP_GLOBAL_Control
0x18000d6e3  cmp     rcx, rax
0x18000d6e6  jz      short loc_18000D733
0x18000d6e8  test    byte ptr [rcx+1Ch], 4
0x18000d6ec  jz      short loc_18000D733
0x18000d6ee  mov     edx, 0Eh
0x18000d6f3  jmp     short loc_18000D727
0x18000d6f5  lea     rdx, [rdi+28h]
0x18000d6f9  mov     ecx, 25h ; '%'; WellKnownSidType
0x18000d6fe  call    RaCreateWellKnownSid
0x18000d703  mov     ebx, eax
0x18000d705  test    eax, eax
0x18000d707  jz      short loc_18000D73B
0x18000d709  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d710  lea     rax, WPP_GLOBAL_Control
0x18000d717  cmp     rcx, rax
0x18000d71a  jz      short loc_18000D733
0x18000d71c  test    byte ptr [rcx+1Ch], 4
0x18000d720  jz      short loc_18000D733
0x18000d722  mov     edx, 0Fh
0x18000d727  mov     rcx, [rcx+10h]
0x18000d72b  mov     r9d, ebx
0x18000d72e  call    WPP_SF_D
0x18000d733  mov     rcx, rdi
0x18000d736  call    RaFreeSidList
0x18000d73b  mov     eax, ebx
0x18000d73d  add     rsp, 20h
0x18000d741  pop     r15
0x18000d743  pop     r14
0x18000d745  pop     r12
0x18000d747  pop     rdi
0x18000d748  pop     rsi
0x18000d749  pop     rbp
0x18000d74a  pop     rbx
0x18000d74b  retn
```

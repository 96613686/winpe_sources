# VsmmCryptGetSecurityCookie

- ea: `0x1400786ac`
- end: `0x14007891d`
- name: `VsmmCryptGetSecurityCookie`
- size: `625`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140035708`

## callees

- `0x1400386a0`
- `0x1400786ac`
- `0x14009b848`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400786e9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400786e9`
- `ntoskrnl!VslRetrieveMailbox` at `0x140078765`
- `ntoskrnl!VslRetrieveMailbox` at `0x1400787e2`
- `ntoskrnl!VslRetrieveMailbox` at `0x140078765`
- `ntoskrnl!VslRetrieveMailbox` at `0x1400787e2`

## string_xrefs

- `0x14007870c`: `VsmmCryptGetSecurityCookie`
- `0x140078735`: `VsmmCryptGetSecurityCookie`
- `0x140078784`: `VsmmCryptGetSecurityCookie`
- `0x1400787ad`: `VsmmCryptGetSecurityCookie`
- `0x140078801`: `VsmmCryptGetSecurityCookie`
- `0x14007882a`: `VsmmCryptGetSecurityCookie`
- `0x14007886d`: `VsmmCryptGetSecurityCookie`
- `0x14007889f`: `VsmmCryptGetSecurityCookie`
- `0x1400788d7`: `VsmmCryptGetSecurityCookie`

## pseudocode

```c
__int64 __fastcall VsmmCryptGetSecurityCookie(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 10240);
  v3 = 8;
  v16 = 8;
  v13 = 8;
  v14 = 0;
  v15 = 0;
  if ( v2 == PsGetCurrentProcess() )
  {
    if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
    {
      v7 = -1073740008;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2731);
      goto LABEL_27;
    }
    LOBYTE(v6) = 2;
    v7 = VslRetrieveMailbox(2, a1 + 9816, v6, &v14, &v16);
    if ( v7 < 0 )
    {
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2746);
      goto LABEL_27;
    }
    if ( v16 != 8 )
    {
      v7 = -1073741788;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2753);
      goto LABEL_27;
    }
    v9 = v14;
    if ( (v14 & 1) == 0 )
    {
      v10 = *(_QWORD *)(a1 + 40) | 8LL;
LABEL_26:
      *(_QWORD *)(a1 + 40) = v10 | 1;
      v7 = 0;
      *a2 = v9;
      goto LABEL_27;
    }
    LOBYTE(v8) = 1;
    v7 = VslRetrieveMailbox(2, a1 + 9816, v8, &v15, &v13);
    if ( v7 < 0 )
    {
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2770);
      goto LABEL_27;
    }
    if ( v13 != 8 )
    {
      v7 = -1073741788;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2776);
      goto LABEL_27;
    }
    if ( v15 == 0x736869656C646700LL )
    {
      if ( (*(_BYTE *)(a1 + 40) & 4) == 0 )
      {
LABEL_21:
        v10 = *(_QWORD *)(a1 + 40);
        if ( (v10 & 2) != 0 )
          v10 |= 8uLL;
        v9 = v14;
        goto LABEL_26;
      }
    }
    else
    {
      if ( v15 != 0x736869656C646701LL )
      {
        v7 = -1073741790;
        VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2783);
        goto LABEL_27;
      }
      if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
      {
        if ( !(unsigned int)VidCurrentProcessIsTrusted(a1) )
        {
          v7 = -1073741790;
          VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2812);
          goto LABEL_27;
        }
        goto LABEL_21;
      }
    }
    v7 = -1073741790;
    VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2797);
    goto LABEL_27;
  }
  v7 = -1073741790;
  VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2721);
LABEL_27:
  v11 = &v14;
  do
  {
    *(_BYTE *)v11 = 0;
    v11 = (__int64 *)((char *)v11 + 1);
    --v3;
  }
  while ( v3 );
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400786ac  mov     [rsp-28h+arg_8], rbx
0x1400786b1  push    rbp
0x1400786b2  push    rsi
0x1400786b3  push    rdi
0x1400786b4  push    r14
0x1400786b6  push    r15
0x1400786b8  mov     rbp, rsp
0x1400786bb  sub     rsp, 40h
0x1400786bf  mov     rbx, [rcx+2800h]
0x1400786c6  mov     esi, 8
0x1400786cb  mov     [rbp+arg_18], rsi
0x1400786cf  mov     r15, rdx
0x1400786d2  mov     [rbp+var_10], rsi
0x1400786d6  mov     rdi, rcx
0x1400786d9  mov     [rbp+arg_0], 0
0x1400786e1  mov     [rbp+arg_10], 0
0x1400786e9  call    cs:__imp_PsGetCurrentProcess
0x1400786f0  nop     dword ptr [rax+rax+00h]
0x1400786f5  cmp     rbx, rax
0x1400786f8  jz      short loc_14007871D
0x1400786fa  mov     ebx, 0C0000022h
0x1400786ff  mov     r8d, 0AA1h
0x140078705  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007870c  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140078713  call    VidTraceErrorInternal0
0x140078718  jmp     loc_1400788F9
0x14007871d  test    byte ptr [rdi+28h], 1
0x140078721  jz      short loc_140078746
0x140078723  mov     ebx, 0C0000718h
0x140078728  mov     r8d, 0AABh
0x14007872e  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078735  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x14007873c  call    VidTraceErrorInternal0
0x140078741  jmp     loc_1400788F9
0x140078746  lea     rax, [rbp+arg_18]
0x14007874a  mov     r8b, 2
0x14007874d  lea     r14, [rdi+2658h]
0x140078754  mov     [rsp+40h+var_20], rax
0x140078759  mov     rdx, r14
0x14007875c  lea     r9, [rbp+arg_0]
0x140078760  mov     ecx, 2
0x140078765  call    cs:__imp_VslRetrieveMailbox
0x14007876c  nop     dword ptr [rax+rax+00h]
0x140078771  mov     ebx, eax
0x140078773  test    eax, eax
0x140078775  jns     short loc_140078795
0x140078777  mov     r8d, 0ABAh
0x14007877d  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078784  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x14007878b  call    VidTraceErrorInternal0
0x140078790  jmp     loc_1400788F9
0x140078795  cmp     [rbp+arg_18], rsi
0x140078799  jz      short loc_1400787BE
0x14007879b  mov     ebx, 0C0000024h
0x1400787a0  mov     r8d, 0AC1h
0x1400787a6  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400787ad  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400787b4  call    VidTraceErrorInternal0
0x1400787b9  jmp     loc_1400788F9
0x1400787be  mov     rax, [rbp+arg_0]
0x1400787c2  test    al, 1
0x1400787c4  jz      loc_1400788E5
0x1400787ca  lea     rax, [rbp+var_10]
0x1400787ce  mov     r8b, 1
0x1400787d1  lea     r9, [rbp+arg_10]
0x1400787d5  mov     [rsp+40h+var_20], rax
0x1400787da  mov     rdx, r14
0x1400787dd  mov     ecx, 2
0x1400787e2  call    cs:__imp_VslRetrieveMailbox
0x1400787e9  nop     dword ptr [rax+rax+00h]
0x1400787ee  mov     ebx, eax
0x1400787f0  test    eax, eax
0x1400787f2  jns     short loc_140078812
0x1400787f4  mov     r8d, 0AD2h
0x1400787fa  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140078801  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140078808  call    VidTraceErrorInternal0
0x14007880d  jmp     loc_1400788F9
0x140078812  cmp     [rbp+var_10], rsi
0x140078816  jz      short loc_14007883B
0x140078818  mov     ebx, 0C0000024h
0x14007881d  mov     r8d, 0AD8h
0x140078823  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007882a  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140078831  call    VidTraceErrorInternal0
0x140078836  jmp     loc_1400788F9
0x14007883b  mov     rax, 736869656C646700h
0x140078845  cmp     [rbp+arg_10], rax
0x140078849  jz      short loc_1400788AD
0x14007884b  mov     rax, 736869656C646701h
0x140078855  cmp     [rbp+arg_10], rax
0x140078859  jz      short loc_14007887B
0x14007885b  mov     ebx, 0C0000022h
0x140078860  mov     r8d, 0ADFh
0x140078866  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007886d  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140078874  call    VidTraceErrorInternal0
0x140078879  jmp     short loc_1400788F9
0x14007887b  test    byte ptr [rdi+28h], 4
0x14007887f  jz      short loc_1400788C5
0x140078881  mov     rcx, rdi
0x140078884  call    VidCurrentProcessIsTrusted
0x140078889  test    eax, eax
0x14007888b  jnz     short loc_1400788B3
0x14007888d  mov     ebx, 0C0000022h
0x140078892  mov     r8d, 0AFCh
0x140078898  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007889f  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400788a6  call    VidTraceErrorInternal0
0x1400788ab  jmp     short loc_1400788F9
0x1400788ad  test    byte ptr [rdi+28h], 4
0x1400788b1  jnz     short loc_1400788C5
0x1400788b3  mov     rcx, [rdi+28h]
0x1400788b7  test    cl, 2
0x1400788ba  jz      short loc_1400788BF
0x1400788bc  or      rcx, rsi
0x1400788bf  mov     rax, [rbp+arg_0]
0x1400788c3  jmp     short loc_1400788EC
0x1400788c5  mov     ebx, 0C0000022h
0x1400788ca  mov     r8d, 0AEDh
0x1400788d0  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400788d7  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400788de  call    VidTraceErrorInternal0
0x1400788e3  jmp     short loc_1400788F9
0x1400788e5  mov     rcx, [rdi+28h]
0x1400788e9  or      rcx, rsi
0x1400788ec  or      rcx, 1
0x1400788f0  mov     [rdi+28h], rcx
0x1400788f4  xor     ebx, ebx
0x1400788f6  mov     [r15], rax
0x1400788f9  lea     rax, [rbp+arg_0]
0x1400788fd  mov     byte ptr [rax], 0
0x140078900  inc     rax
0x140078903  sub     rsi, 1
0x140078907  jnz     short loc_1400788FD
0x140078909  mov     eax, ebx
0x14007890b  mov     rbx, [rsp+40h+arg_8]
0x140078910  add     rsp, 40h
0x140078914  pop     r15
0x140078916  pop     r14
0x140078918  pop     rdi
0x140078919  pop     rsi
0x14007891a  pop     rbp
0x14007891b  retn
```

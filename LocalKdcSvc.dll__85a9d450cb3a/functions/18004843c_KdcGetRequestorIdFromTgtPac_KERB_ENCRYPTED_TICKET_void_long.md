# KdcGetRequestorIdFromTgtPac(KERB_ENCRYPTED_TICKET *,void * *,long *)

- ea: `0x18004843c`
- end: `0x1800485db`
- name: `?KdcGetRequestorIdFromTgtPac@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAPEAXPEAJ@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct KERB_ENCRYPTED_TICKET *, void **, int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d42c`
- `0x180029844`
- `0x18005e9ac`

## callees

- `0x1800038f0`
- `0x18000a814`
- `0x18000a84c`
- `0x1800101c4`
- `0x180045388`
- `0x18004843c`
- `0x18005a060`
- `0x18006fc78`
- `0x180070f30`
- `0x18007f69c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180048558`
- `ntdll!RtlLengthSid` at `0x180048574`
- `ntdll!RtlLengthSid` at `0x1800485a6`
- `ntdll!RtlLengthSid` at `0x180048558`
- `ntdll!RtlLengthSid` at `0x180048574`
- `ntdll!RtlLengthSid` at `0x1800485a6`
- `ntdll!RtlValidSid` at `0x180048566`
- `ntdll!RtlValidSid` at `0x180048566`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcGetRequestorIdFromTgtPac(struct KERB_ENCRYPTED_TICKET *a1, void **a2, int *a3)
{
  __int64 v5; // rax
  __int64 v6; // r10
  unsigned int PacFromAuthData; // eax
  unsigned int v8; // ebx
  struct _PACTYPE *v9; // rbx
  struct _PAC_INFO_BUFFER *v10; // r8
  struct _PAC_INFO_BUFFER *v12; // rax
  struct _PAC_INFO_BUFFER *v13; // rdi
  ULONG v14; // ebx
  ULONG v15; // eax
  ULONG v16; // eax
  _BYTE v17[16]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v18[32]; // [rsp+30h] [rbp-20h] BYREF
  void *v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  v20 = 0;
  v21 = 0;
  v19 = 0;
  *a3 = 0;
  v5 = lambda_14fd01bcd5a8d1a80ee3c701b30d75de_::_lambda_14fd01bcd5a8d1a80ee3c701b30d75de_(v17, &v20, &v19);
  wil::scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___(v18, v5);
  if ( (*(_BYTE *)v6 & 0x10) == 0 )
    goto LABEL_10;
  PacFromAuthData = KerbGetPacFromAuthData(*(_QWORD *)(v6 + 160), &v20, 0, &v21);
  v8 = PacFromAuthData;
  if ( !v21 )
  {
    *a3 = 0;
LABEL_18:
    v8 = 60;
    goto LABEL_19;
  }
  if ( PacFromAuthData )
  {
    *a3 = -1073741801;
LABEL_19:
    wil::details::lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___::_lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___(v18);
    return v8;
  }
  v9 = *(struct _PACTYPE **)(v21 + 24);
  if ( !PAC_UnMarshal(v9, *(_DWORD *)(v21 + 16)) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    goto LABEL_10;
  }
  v12 = PAC_Find(v9, 0x12u, v10);
  v13 = v12;
  if ( !v12 )
  {
    *a3 = -1073741275;
    goto LABEL_18;
  }
  if ( *((_DWORD *)v12 + 1) < 0xCu
    || (v14 = *((_DWORD *)v12 + 1), v14 < RtlLengthSid(*((PSID *)v12 + 1)))
    || !RtlValidSid(*((PSID *)v13 + 1)) )
  {
LABEL_10:
    *a3 = -1073741811;
    wil::details::lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___::_lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___(v18);
    return 60;
  }
  v15 = RtlLengthSid(*((PSID *)v13 + 1));
  v19 = MIDL_user_allocate(v15);
  if ( !v19 )
  {
    *a3 = -1073741801;
    goto LABEL_18;
  }
  v16 = RtlLengthSid(*((PSID *)v13 + 1));
  memcpy_0(v19, *((const void **)v13 + 1), v16);
  *a2 = v19;
  v19 = 0;
  wil::details::lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___::_lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___(v18);
  return 0;
}

```

## disassembly

```asm
0x18004843c  push    rbp
0x18004843e  push    rbx
0x18004843f  push    rsi
0x180048440  push    rdi
0x180048441  push    r14
0x180048443  mov     rbp, rsp
0x180048446  sub     rsp, 50h
0x18004844a  mov     rsi, r8
0x18004844d  mov     r14, rdx
0x180048450  mov     r10, rcx
0x180048453  mov     [rbp+arg_10], 0
0x18004845b  mov     [rbp+arg_18], 0
0x180048463  mov     [rbp+arg_0], 0
0x18004846b  mov     dword ptr [r8], 0
0x180048472  lea     r8, [rbp+arg_0]
0x180048476  lea     rdx, [rbp+arg_10]
0x18004847a  lea     rcx, [rbp+var_30]
0x18004847e  call    _lambda_14fd01bcd5a8d1a80ee3c701b30d75de____lambda_14fd01bcd5a8d1a80ee3c701b30d75de_
0x180048483  mov     rdx, rax
0x180048486  lea     rcx, [rbp+var_20]
0x18004848a  call    wil__scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___
0x18004848f  nop
0x180048490  test    byte ptr [r10], 10h
0x180048494  jz      short loc_18004850F
0x180048496  lea     r9, [rbp+arg_18]
0x18004849a  xor     r8d, r8d
0x18004849d  lea     rdx, [rbp+arg_10]
0x1800484a1  mov     rcx, [r10+0A0h]
0x1800484a8  call    KerbGetPacFromAuthData
0x1800484ad  mov     ebx, eax
0x1800484af  mov     rdx, [rbp+arg_18]
0x1800484b3  test    rdx, rdx
0x1800484b6  jnz     short loc_1800484BF
0x1800484b8  mov     [rsi], edx
0x1800484ba  jmp     loc_180048590
0x1800484bf  test    eax, eax
0x1800484c1  jz      short loc_1800484CE
0x1800484c3  mov     dword ptr [rsi], 0C0000017h
0x1800484c9  jmp     loc_180048595
0x1800484ce  mov     rbx, [rdx+18h]
0x1800484d2  mov     edx, [rdx+10h]; unsigned int
0x1800484d5  mov     rcx, rbx; struct _PACTYPE *
0x1800484d8  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x1800484dd  test    eax, eax
0x1800484df  jnz     short loc_18004852E
0x1800484e1  lea     rax, WPP_GLOBAL_Control
0x1800484e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484ef  cmp     rcx, rax
0x1800484f2  jz      short loc_18004850F
0x1800484f4  test    byte ptr [rcx+1Ch], 1
0x1800484f8  jz      short loc_18004850F
0x1800484fa  mov     edx, 81h
0x1800484ff  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180048506  mov     rcx, [rcx+10h]
0x18004850a  call    WPP_SF_
0x18004850f  mov     dword ptr [rsi], 0C000000Dh
0x180048515  lea     rcx, [rbp+var_20]
0x180048519  call    wil__details__lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a______lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___
0x18004851e  mov     eax, 3Ch ; '<'
0x180048523  add     rsp, 50h
0x180048527  pop     r14
0x180048529  pop     rdi
0x18004852a  pop     rsi
0x18004852b  pop     rbx
0x18004852c  pop     rbp
0x18004852d  retn
0x18004852e  mov     edx, 12h; unsigned int
0x180048533  mov     rcx, rbx; struct _PACTYPE *
0x180048536  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18004853b  mov     rdi, rax
0x18004853e  test    rax, rax
0x180048541  jnz     short loc_18004854B
0x180048543  mov     dword ptr [rsi], 0C0000225h
0x180048549  jmp     short loc_180048590
0x18004854b  cmp     dword ptr [rax+4], 0Ch
0x18004854f  jb      short loc_18004850F
0x180048551  mov     ebx, [rax+4]
0x180048554  mov     rcx, [rax+8]; Sid
0x180048558  call    cs:__imp_RtlLengthSid
0x18004855e  cmp     ebx, eax
0x180048560  jb      short loc_18004850F
0x180048562  mov     rcx, [rdi+8]; Sid
0x180048566  call    cs:__imp_RtlValidSid
0x18004856c  test    al, al
0x18004856e  jz      short loc_18004850F
0x180048570  mov     rcx, [rdi+8]; Sid
0x180048574  call    cs:__imp_RtlLengthSid
0x18004857a  mov     ecx, eax; size
0x18004857c  call    MIDL_user_allocate
0x180048581  mov     [rbp+arg_0], rax
0x180048585  test    rax, rax
0x180048588  jnz     short loc_1800485A2
0x18004858a  mov     dword ptr [rsi], 0C0000017h
0x180048590  mov     ebx, 3Ch ; '<'
0x180048595  lea     rcx, [rbp+var_20]
0x180048599  call    wil__details__lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a______lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___
0x18004859e  mov     eax, ebx
0x1800485a0  jmp     short loc_180048523
0x1800485a2  mov     rcx, [rdi+8]; Sid
0x1800485a6  call    cs:__imp_RtlLengthSid
0x1800485ac  mov     r8d, eax; Size
0x1800485af  mov     rdx, [rdi+8]; Src
0x1800485b3  mov     rcx, [rbp+arg_0]; void *
0x1800485b7  call    memcpy_0
0x1800485bc  mov     rax, [rbp+arg_0]
0x1800485c0  mov     [r14], rax
0x1800485c3  mov     [rbp+arg_0], 0
0x1800485cb  lea     rcx, [rbp+var_20]
0x1800485cf  call    wil__details__lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a______lambda_call__lambda_3952001c73ab5c984b69a0dd325f265a___
0x1800485d4  xor     eax, eax
0x1800485d6  jmp     loc_180048523
```

# Broker::BILayer::NotificationChannel::ProcessWnfEvent(Broker::BILayer::NotificationChannel::Event,unsigned __int64,void const *)

- ea: `0x18000bfd0`
- end: `0x18000c26c`
- name: `?ProcessWnfEvent@NotificationChannel@BILayer@Broker@@QEAAXW4Event@123@_KPEBX@Z`
- size: `668`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf70`
- `0x18000bf90`
- `0x18000bfb0`
- `0x180012fe0`
- `0x180013210`
- `0x180014290`
- `0x18001a700`

## callees

- `0x180009e94`
- `0x18000bfd0`
- `0x18000c274`
- `0x1800165da`
- `0x18001a7f0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c020`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c11d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c24f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c020`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c11d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c24f`

## pseudocode

```c
void __fastcall Broker::BILayer::NotificationChannel::ProcessWnfEvent(
        __int64 a1,
        signed int a2,
        unsigned __int64 a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  __int64 v6; // rax
  char *v7; // rsi
  char *v8; // r14
  __int64 v9; // rax
  char *v10; // r15
  __int64 v11; // rcx
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // r14d
  int v16; // r15d
  char *v17; // r12
  unsigned int *v18; // rsi
  __int64 v19; // r10
  __int64 v20; // rcx
  unsigned int v21; // [rsp+30h] [rbp-78h] BYREF
  unsigned int *v22; // [rsp+38h] [rbp-70h] BYREF
  char *v23; // [rsp+40h] [rbp-68h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-60h] BYREF
  __int128 v25; // [rsp+50h] [rbp-58h]
  int v26; // [rsp+60h] [rbp-48h]
  int v27; // [rsp+C8h] [rbp+20h] BYREF

  v4 = a2;
  if ( !a4 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)a2);
    return;
  }
  if ( a2 == 6 )
    goto LABEL_3;
  if ( a2 != 3 )
  {
    if ( (unsigned int)a2 <= 1 )
    {
      if ( a3 >= 0x18 )
      {
        v15 = *a4;
        v16 = a4[4];
        v17 = (char *)*((_QWORD *)a4 + 1);
        v18 = a4 + 5;
        if ( !IsValidSid(a4 + 5) )
          v18 = 0;
        v19 = *(_QWORD *)(a1 + 24) + (v4 << 8);
        v20 = *(_QWORD *)(v19 + 184);
        if ( v20 )
        {
          v22 = v18;
          v27 = v16;
          v23 = v17;
          v21 = v15;
          (*(void (__fastcall **)(__int64, unsigned int *, char **, int *, unsigned int **))(*(_QWORD *)v20 + 16LL))(
            v20,
            &v21,
            &v23,
            &v27,
            &v22);
        }
        else if ( *(_QWORD *)(v19 + 56) )
        {
          std::_Func_class<void,unsigned long,unsigned short const *,void *>::operator()(
            *(_QWORD *)(a1 + 24) + (v4 << 8),
            v15,
            0,
            v18);
        }
      }
      return;
    }
    if ( a2 != 2 )
    {
      if ( (unsigned int)(a2 - 4) > 1 )
        return;
LABEL_3:
      if ( a3 < 0xC )
      {
        v25 = 0;
        v26 = 4;
        pExceptionObject = &Broker::InvalidParameter::`vftable';
        throw (Broker::InvalidParameter *)&pExceptionObject;
      }
      v6 = a4[1];
      v7 = 0;
      if ( (_DWORD)v6 )
      {
        v8 = (char *)a4 + v6;
      }
      else
      {
        try
        {
          v8 = 0;
        }
        catch ( Broker::InvalidParameter )
        {
          return;
        }
      }
      v9 = *a4;
      if ( (_DWORD)v9 )
      {
        v10 = (char *)a4 + v9;
        if ( IsValidSid((char *)a4 + v9) )
        {
          v7 = v10;
        }
        else if ( !IsValidSid(v10) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
      v11 = *(_QWORD *)((v4 << 8) + *(_QWORD *)(a1 + 24) + 56);
      if ( v11 )
      {
        v22 = (unsigned int *)v8;
        v27 = -1;
LABEL_11:
        v23 = v7;
        (*(void (__fastcall **)(__int64, int *, unsigned int **, char **))(*(_QWORD *)v11 + 16LL))(
          v11,
          &v27,
          &v22,
          &v23);
        return;
      }
      return;
    }
  }
  if ( a3 >= 4 )
  {
    v12 = *a4;
    v13 = *(_QWORD *)(a1 + 24);
    v14 = *(_QWORD *)(((__int64)a2 << 8) + v13 + 248);
    if ( v14 )
    {
      v27 = *a4;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 16LL))(v14, &v27);
    }
    else
    {
      v11 = *(_QWORD *)(((__int64)a2 << 8) + v13 + 56);
      if ( v11 )
      {
        v7 = 0;
        v22 = 0;
        v27 = v12;
        goto LABEL_11;
      }
    }
  }
}

```

## disassembly

```asm
0x18000bfd0  push    rbx
0x18000bfd2  push    rsi
0x18000bfd3  push    rdi
0x18000bfd4  push    r12
0x18000bfd6  push    r14
0x18000bfd8  push    r15
0x18000bfda  sub     rsp, 78h
0x18000bfde  movsxd  rbx, edx
0x18000bfe1  mov     rdi, rcx
0x18000bfe4  test    r9, r9
0x18000bfe7  jz      loc_18000C1E0
0x18000bfed  cmp     ebx, 6
0x18000bff0  jnz     loc_18000C087
0x18000bff6  cmp     r8, 0Ch
0x18000bffa  jb      loc_18000C21F
0x18000c000  mov     eax, [r9+4]
0x18000c004  xor     esi, esi
0x18000c006  test    eax, eax
0x18000c008  jz      loc_18000C1B8
0x18000c00e  lea     r14, [r9+rax]
0x18000c012  mov     eax, [r9]
0x18000c015  test    eax, eax
0x18000c017  jz      short loc_18000C031
0x18000c019  lea     r15, [r9+rax]
0x18000c01d  mov     rcx, r15; pSid
0x18000c020  call    cs:__imp_IsValidSid
0x18000c026  test    eax, eax
0x18000c028  jz      loc_18000C24C
0x18000c02e  mov     rsi, r15
0x18000c031  mov     rcx, rbx
0x18000c034  shl     rcx, 8
0x18000c038  mov     rax, [rdi+18h]
0x18000c03c  mov     rcx, [rcx+rax+38h]
0x18000c041  test    rcx, rcx
0x18000c044  jz      short loc_18000C079
0x18000c046  mov     [rsp+0A8h+var_70], r14
0x18000c04b  mov     [rsp+0A8h+arg_18], 0FFFFFFFFh
0x18000c056  mov     [rsp+0A8h+var_68], rsi
0x18000c05b  mov     rax, [rcx]
0x18000c05e  lea     r9, [rsp+0A8h+var_68]
0x18000c063  lea     r8, [rsp+0A8h+var_70]
0x18000c068  lea     rdx, [rsp+0A8h+arg_18]
0x18000c070  mov     rax, [rax+10h]
0x18000c074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c079  add     rsp, 78h
0x18000c07d  pop     r15
0x18000c07f  pop     r14
0x18000c081  pop     r12
0x18000c083  pop     rdi
0x18000c084  pop     rsi
0x18000c085  pop     rbx
0x18000c086  retn
0x18000c087  cmp     ebx, 3
0x18000c08a  jnz     short loc_18000C0F2
0x18000c08c  cmp     r8, 4
0x18000c090  jb      short loc_18000C079
0x18000c092  mov     r8d, [r9]
0x18000c095  mov     rdx, rbx
0x18000c098  shl     rdx, 8
0x18000c09c  mov     rax, [rdi+18h]
0x18000c0a0  mov     rcx, [rdx+rax+0F8h]
0x18000c0a8  test    rcx, rcx
0x18000c0ab  jnz     short loc_18000C0C8
0x18000c0ad  mov     rcx, [rdx+rax+38h]
0x18000c0b2  test    rcx, rcx
0x18000c0b5  jz      short loc_18000C079
0x18000c0b7  xor     esi, esi
0x18000c0b9  mov     [rsp+0A8h+var_70], rsi
0x18000c0be  mov     [rsp+0A8h+arg_18], r8d
0x18000c0c6  jmp     short loc_18000C056
0x18000c0c8  mov     [rsp+0A8h+arg_18], r8d
0x18000c0d0  mov     rax, [rcx]
0x18000c0d3  lea     rdx, [rsp+0A8h+arg_18]
0x18000c0db  mov     rax, [rax+10h]
0x18000c0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e4  add     rsp, 78h
0x18000c0e8  pop     r15
0x18000c0ea  pop     r14
0x18000c0ec  pop     r12
0x18000c0ee  pop     rdi
0x18000c0ef  pop     rsi
0x18000c0f0  pop     rbx
0x18000c0f1  retn
0x18000c0f2  mov     ecx, ebx
0x18000c0f4  test    edx, edx
0x18000c0f6  jz      short loc_18000C101
0x18000c0f8  sub     ecx, 1
0x18000c0fb  jnz     loc_18000C1C0
0x18000c101  cmp     r8, 18h
0x18000c105  jb      loc_18000C079
0x18000c10b  mov     r14d, [r9]
0x18000c10e  mov     r15d, [r9+10h]
0x18000c112  mov     r12, [r9+8]
0x18000c116  lea     rsi, [r9+14h]
0x18000c11a  mov     rcx, rsi; pSid
0x18000c11d  call    cs:__imp_IsValidSid
0x18000c123  test    eax, eax
0x18000c125  jz      loc_18000C218
0x18000c12b  mov     r10, rbx
0x18000c12e  shl     r10, 8
0x18000c132  add     r10, [rdi+18h]
0x18000c136  mov     rcx, [r10+0B8h]
0x18000c13d  test    rcx, rcx
0x18000c140  jz      short loc_18000C18F
0x18000c142  mov     [rsp+0A8h+var_70], rsi
0x18000c147  mov     [rsp+0A8h+arg_18], r15d
0x18000c14f  mov     [rsp+0A8h+var_68], r12
0x18000c154  mov     [rsp+0A8h+var_78], r14d
0x18000c159  mov     rax, [rcx]
0x18000c15c  lea     rdx, [rsp+0A8h+var_70]
0x18000c161  mov     [rsp+0A8h+var_88], rdx
0x18000c166  lea     r9, [rsp+0A8h+arg_18]
0x18000c16e  lea     r8, [rsp+0A8h+var_68]
0x18000c173  lea     rdx, [rsp+0A8h+var_78]
0x18000c178  mov     rax, [rax+10h]
0x18000c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c181  add     rsp, 78h
0x18000c185  pop     r15
0x18000c187  pop     r14
0x18000c189  pop     r12
0x18000c18b  pop     rdi
0x18000c18c  pop     rsi
0x18000c18d  pop     rbx
0x18000c18e  retn
0x18000c18f  cmp     qword ptr [r10+38h], 0
0x18000c194  jz      loc_18000C079
0x18000c19a  mov     r9, rsi
0x18000c19d  xor     r8d, r8d
0x18000c1a0  mov     edx, r14d
0x18000c1a3  mov     rcx, r10
0x18000c1a6  add     rsp, 78h
0x18000c1aa  pop     r15
0x18000c1ac  pop     r14
0x18000c1ae  pop     r12
0x18000c1b0  pop     rdi
0x18000c1b1  pop     rsi
0x18000c1b2  pop     rbx
0x18000c1b3  jmp     ??R?$_Func_class@XKPEBGPEAX@std@@QEBAXKPEBGPEAX@Z; std::_Func_class<void,ulong,ushort const *,void *>::operator()(ulong,ushort const *,void *)
0x18000c1b8  mov     r14, rsi
0x18000c1bb  jmp     loc_18000C012
0x18000c1c0  sub     ecx, 1
0x18000c1c3  jz      loc_18000C08C
0x18000c1c9  sub     ecx, 2
0x18000c1cc  jz      loc_18000BFF6
0x18000c1d2  cmp     ecx, 1
0x18000c1d5  jnz     loc_18000C079
0x18000c1db  jmp     loc_18000BFF6
0x18000c1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e7  test    byte ptr [rcx+1Ch], 1
0x18000c1eb  jz      loc_18000C079
0x18000c1f1  cmp     byte ptr [rcx+19h], 2
0x18000c1f5  jb      loc_18000C079
0x18000c1fb  mov     edx, 28h ; '('
0x18000c200  mov     r9d, ebx
0x18000c203  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000c20a  mov     rcx, [rcx+10h]
0x18000c20e  call    WPP_SF_d
0x18000c213  jmp     loc_18000C079
0x18000c218  xor     esi, esi
0x18000c21a  jmp     loc_18000C12B
0x18000c21f  xorps   xmm0, xmm0
0x18000c222  movups  [rsp+0A8h+var_58], xmm0
0x18000c227  mov     [rsp+0A8h+var_48], 4
0x18000c22f  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000c236  mov     [rsp+0A8h+pExceptionObject], rax
0x18000c23b  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000c242  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000c247  call    _CxxThrowException_0
0x18000c24c  mov     rcx, r15; pSid
0x18000c24f  call    cs:__imp_IsValidSid
0x18000c255  test    eax, eax
0x18000c257  jnz     loc_18000C031
0x18000c25d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c262  jmp     loc_18000C031
0x18000c267  jmp     loc_18000C079
```

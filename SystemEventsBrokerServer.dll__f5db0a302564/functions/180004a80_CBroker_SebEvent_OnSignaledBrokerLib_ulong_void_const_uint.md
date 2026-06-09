# CBroker::SebEvent::OnSignaledBrokerLib(ulong,void const *,uint)

- ea: `0x180004a80`
- end: `0x180005220`
- name: `?OnSignaledBrokerLib@SebEvent@CBroker@@QEAAXKPEBXI@Z`
- size: `1952`
- prototype: `void __fastcall(CBroker::SebEvent *__hidden this, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x180003120`
- `0x180003950`
- `0x180003af0`
- `0x180003b60`
- `0x180004a80`
- `0x180005a50`
- `0x180008c00`
- `0x18001cf50`
- `0x180020a10`
- `0x180022434`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ac1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ac1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004c4d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004c4d`
- `ntdll!RtlWakeAddressAll` at `0x180004dca`
- `ntdll!RtlWakeAddressAll` at `0x1800051c2`
- `ntdll!RtlWakeAddressAll` at `0x180004dca`
- `ntdll!RtlWakeAddressAll` at `0x1800051c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ac7`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180004c0f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180004d93`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180004c0f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180004d93`

## pseudocode

```c
void __fastcall CBroker::SebEvent::OnSignaledBrokerLib(
        CBroker::SebEvent *this,
        unsigned int a2,
        char *a3,
        unsigned int a4)
{
  __int64 v5; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  _BYTE *v10; // rdi
  int v11; // eax
  unsigned __int64 v12; // rcx
  int v13; // ebp
  int v14; // eax
  int v15; // edx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // ebp
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned int v24; // ecx
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  unsigned int v28; // eax
  int v29; // ecx
  int v30; // eax
  _BYTE v31[8]; // [rsp+30h] [rbp-58h] BYREF
  GUID v32; // [rsp+38h] [rbp-50h] BYREF

  v5 = a4;
  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  v32 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_Ld(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      (char *)this + 120,
      *((_DWORD *)this + 24),
      *((_DWORD *)this + 38));
    v10 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 39) || !*((_BYTE *)this + 161) )
  {
    v11 = *((_DWORD *)this + 38);
    if ( !v11 || v11 == 3 )
    {
      if ( (v10[28] & 0x40) == 0 || v10[25] < 2u )
        goto LABEL_26;
      WPP_SF_(*((_QWORD *)v10 + 2), 60, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids);
      goto LABEL_25;
    }
    if ( *((_DWORD *)this + 24) != 4148 )
    {
      v12 = *((unsigned int *)this + 44);
      if ( v5 + 8 < v12 )
      {
        if ( (v10[28] & 0x40) == 0 || v10[25] < 2u )
          goto LABEL_26;
        v23 = 61;
        goto LABEL_90;
      }
      if ( (unsigned int)v12 > 8 && !a3 )
      {
        if ( (v10[28] & 0x40) == 0 || v10[25] < 2u )
          goto LABEL_26;
        v23 = 62;
LABEL_90:
        WPP_SF__guid_dd(*((_QWORD *)v10 + 2), v23, v9, (char *)this + 120, v5, v12);
        goto LABEL_25;
      }
      if ( *((_DWORD *)this + 25) )
      {
        v13 = 0;
        if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
        {
          WPP_SF_DDd(*((_QWORD *)v10 + 2), 83, v9, *((unsigned int *)this + 28), *((_DWORD *)this + 29), a2);
          v10 = WPP_GLOBAL_Control;
        }
        v14 = *((_DWORD *)this + 25);
        if ( v14 == 4 )
        {
          switch ( *((_DWORD *)this + 52) )
          {
            case 1:
              goto LABEL_100;
            case 2:
              goto LABEL_54;
            case 3:
              LOBYTE(v13) = a2 > *((_DWORD *)this + 62);
              break;
            case 4:
              LOBYTE(v13) = a2 >= *((_DWORD *)this + 62);
              break;
            case 5:
              LOBYTE(v13) = a2 < *((_DWORD *)this + 62);
              break;
            case 6:
              LOBYTE(v13) = a2 <= *((_DWORD *)this + 62);
              break;
            default:
              break;
          }
        }
        else if ( (unsigned int)(v14 - 1) <= 2 )
        {
          if ( *((_DWORD *)this + 52) == 1 )
          {
LABEL_100:
            LOBYTE(v13) = *((_DWORD *)this + 62) == a2;
          }
          else if ( *((_DWORD *)this + 52) == 2 )
          {
LABEL_54:
            LOBYTE(v13) = *((_DWORD *)this + 62) != a2;
          }
        }
        if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
        {
          WPP_SF_DDd(*((_QWORD *)v10 + 2), 84, &_ImageBase, *((unsigned int *)this + 28), *((_DWORD *)this + 29), v13);
          v10 = WPP_GLOBAL_Control;
        }
        v15 = *((unsigned __int8 *)this + 160);
        if ( (_BYTE)v15 == (_BYTE)v13 && (byte_180035F64[40 * *((int *)this + 24) - 163840] & 2) == 0 )
        {
          if ( (v10[28] & 0x40) == 0 || v10[25] < 4u )
            goto LABEL_26;
          WPP_SF__guid_D(
            *((_QWORD *)v10 + 2),
            63,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            (char *)this + 120,
            v15);
          goto LABEL_25;
        }
        *((_BYTE *)this + 160) = v13;
        v10 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            (char *)this + 120,
            (unsigned __int8)v13);
          v10 = WPP_GLOBAL_Control;
        }
        v16 = *((_DWORD *)this + 25);
        if ( v16 == 2 )
        {
          if ( !(_BYTE)v13 )
            goto LABEL_26;
        }
        else if ( v16 == 3 && (_BYTE)v13 == 1 )
        {
          goto LABEL_26;
        }
      }
      else
      {
        LOBYTE(v13) = 1;
        *((_BYTE *)this + 160) = 1;
      }
LABEL_23:
      v17 = *((_DWORD *)this + 25);
      if ( v17 == 1 || v17 == 4 )
      {
        v18 = *((_QWORD *)this + 18);
        v19 = *((_QWORD *)this + 17);
        v31[0] = v13;
        if ( (int)BrSignalBrokerEvent2(v19, v18, v31, &v32, 0, 0) < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_26;
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            (char *)this + 120);
        }
      }
      else
      {
        if ( *((_DWORD *)this + 39) )
          *((_BYTE *)this + 161) = 1;
        if ( (int)BrSignalBrokerEvent2(*((_QWORD *)this + 17), *((_QWORD *)this + 18), 0, &v32, v5, a3) < 0
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            (char *)this + 120);
        }
        if ( *((_DWORD *)this + 39) )
        {
          *((_BYTE *)this + 161) = 1;
          *((_DWORD *)this + 38) = 3;
        }
        else
        {
          *((_QWORD *)this + 25) = 0;
          *((_DWORD *)this + 38) = 1;
        }
        RtlWakeAddressAll((char *)this + 152, v22);
      }
      goto LABEL_25;
    }
    if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
    {
      WPP_SF_DD(
        *((_QWORD *)v10 + 2),
        85,
        &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
        *((unsigned int *)this + 28),
        *((_DWORD *)this + 29));
      v10 = WPP_GLOBAL_Control;
    }
    v20 = *((_QWORD *)this + 32);
    if ( !v20 )
      goto LABEL_35;
    if ( !*(_QWORD *)v20 )
      goto LABEL_35;
    v24 = *(_DWORD *)(v20 + 8);
    if ( !v24 )
      goto LABEL_35;
    v25 = *(unsigned int *)(v20 + 12);
    v21 = 0;
    if ( (unsigned int)v5 < (unsigned int)v25 + v24 )
      goto LABEL_36;
    v26 = memcmp_0(&a3[v25], *(const void **)v20, v24);
    if ( !v26 )
    {
      v28 = *((_DWORD *)this + 52);
      if ( v28 > 6 )
        goto LABEL_36;
      v29 = 82;
      if ( !_bittest(&v29, v28) )
        goto LABEL_36;
      goto LABEL_35;
    }
    if ( v26 <= 0 )
    {
      v30 = *((_DWORD *)this + 52);
      if ( v30 == 5 || v30 == 6 )
        goto LABEL_35;
    }
    else
    {
      v27 = *((_DWORD *)this + 52);
      if ( v27 == 3 || v27 == 4 )
        goto LABEL_35;
    }
    if ( *((_DWORD *)this + 52) != 2 )
    {
LABEL_36:
      if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
      {
        WPP_SF_DDd(*((_QWORD *)v10 + 2), 86, v9, *((unsigned int *)this + 28), *((_DWORD *)this + 29), v21);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v21 )
      {
        LOBYTE(v13) = 0;
        if ( (_DWORD)v5 )
          v32 = CBroker::CLSID_CustomSystemTriggerDataFactory;
        if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
          WPP_SF_DD(
            *((_QWORD *)v10 + 2),
            66,
            &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
            *((unsigned int *)this + 28),
            *((_DWORD *)this + 29));
        goto LABEL_23;
      }
      if ( (v10[28] & 0x40) == 0 || v10[25] < 4u )
        goto LABEL_26;
      WPP_SF_DD(
        *((_QWORD *)v10 + 2),
        65,
        &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
        *((unsigned int *)this + 28),
        *((_DWORD *)this + 29));
LABEL_25:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
LABEL_35:
    v21 = 1;
    goto LABEL_36;
  }
  if ( (v10[28] & 0x40) != 0 && v10[25] >= 2u )
  {
    WPP_SF__guid_(*((_QWORD *)v10 + 2), 59, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( (v10[28] & 0x40) != 0 && v10[25] >= 4u )
    WPP_SF__guid_(*((_QWORD *)v10 + 2), 69, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
  RtlReleaseSRWLockExclusive((char *)this + 240);
}

```

## disassembly

```asm
0x180004a80  push    rbx
0x180004a82  push    rsi
0x180004a83  push    rdi
0x180004a84  sub     rsp, 70h
0x180004a88  mov     rax, cs:__security_cookie
0x180004a8f  xor     rax, rsp
0x180004a92  mov     [rsp+88h+var_40], rax
0x180004a97  mov     [rsp+88h+var_20], r12
0x180004a9c  mov     rbx, rcx
0x180004a9f  mov     [rsp+88h+var_28], r13
0x180004aa4  xorps   xmm0, xmm0
0x180004aa7  mov     [rsp+88h+var_38], r15
0x180004aac  add     rcx, 0F0h
0x180004ab3  mov     r15d, r9d
0x180004ab6  mov     r13, r8
0x180004ab9  mov     r12d, edx
0x180004abc  movups  [rsp+88h+var_50], xmm0
0x180004ac1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004ac7  call    cs:__imp_GetCurrentThreadId
0x180004acd  xorps   xmm0, xmm0
0x180004ad0  movups  [rsp+88h+var_50], xmm0
0x180004ad5  mov     rdi, cs:WPP_GLOBAL_Control
0x180004adc  test    byte ptr [rdi+1Ch], 40h
0x180004ae0  jnz     loc_180004C68
0x180004ae6  cmp     dword ptr [rbx+9Ch], 0
0x180004aed  mov     [rsp+88h+arg_8], rbp
0x180004af5  jnz     loc_180004F25
0x180004afb  mov     eax, [rbx+98h]
0x180004b01  mov     [rsp+88h+var_30], r14
0x180004b06  test    eax, eax
0x180004b08  jz      loc_180004D2F
0x180004b0e  cmp     eax, 3
0x180004b11  jz      loc_180004D2F
0x180004b17  cmp     dword ptr [rbx+60h], 1034h
0x180004b1e  jz      loc_180004CBD
0x180004b24  mov     ecx, [rbx+0B0h]
0x180004b2a  lea     rax, [r15+8]
0x180004b2e  cmp     rax, rcx
0x180004b31  jb      loc_180004EDD
0x180004b37  cmp     ecx, 8
0x180004b3a  ja      loc_1800050AF
0x180004b40  cmp     dword ptr [rbx+64h], 0
0x180004b44  jz      loc_180004BCB
0x180004b4a  xor     ebp, ebp
0x180004b4c  test    byte ptr [rdi+1Ch], 40h
0x180004b50  jz      short loc_180004B5C
0x180004b52  cmp     byte ptr [rdi+19h], 4
0x180004b56  jnb     loc_180004EFB
0x180004b5c  mov     eax, [rbx+64h]
0x180004b5f  lea     r8, __ImageBase
0x180004b66  cmp     eax, 4
0x180004b69  jnz     loc_180004DD5
0x180004b6f  mov     eax, [rbx+0D0h]
0x180004b75  dec     eax; switch 6 cases
0x180004b77  cmp     eax, 5
0x180004b7a  jbe     loc_1800050CE
0x180004b80  test    byte ptr [rdi+1Ch], 40h; jumptable 00000001800050DB default case
0x180004b84  jnz     loc_180004EA3
0x180004b8a  movzx   edx, byte ptr [rbx+0A0h]
0x180004b91  cmp     dl, bpl
0x180004b94  jz      loc_180004FED
0x180004b9a  mov     [rbx+0A0h], bpl
0x180004ba1  mov     rdi, cs:WPP_GLOBAL_Control
0x180004ba8  test    byte ptr [rdi+1Ch], 40h
0x180004bac  jz      short loc_180004BB8
0x180004bae  cmp     byte ptr [rdi+19h], 4
0x180004bb2  jnb     loc_180004F6B
0x180004bb8  mov     eax, [rbx+64h]
0x180004bbb  cmp     eax, 2
0x180004bbe  jnz     loc_180004E08
0x180004bc4  test    bpl, bpl
0x180004bc7  jnz     short loc_180004BD5
0x180004bc9  jmp     short loc_180004C24
0x180004bcb  mov     bpl, 1
0x180004bce  mov     [rbx+0A0h], bpl
0x180004bd5  mov     eax, [rbx+64h]
0x180004bd8  cmp     eax, 1
0x180004bdb  jnz     loc_180004D5D
0x180004be1  mov     rdx, [rbx+90h]
0x180004be8  lea     r9, [rsp+88h+var_50]
0x180004bed  mov     rcx, [rbx+88h]
0x180004bf4  lea     r8, [rsp+88h+var_58]
0x180004bf9  mov     [rsp+88h+var_60], 0
0x180004c02  mov     [rsp+88h+var_68], 0
0x180004c0a  mov     [rsp+88h+var_58], bpl
0x180004c0f  call    cs:__imp_BrSignalBrokerEvent2
0x180004c15  test    eax, eax
0x180004c17  js      loc_1800051CD
0x180004c1d  mov     rdi, cs:WPP_GLOBAL_Control
0x180004c24  mov     r14, [rsp+88h+var_30]
0x180004c29  mov     r15, [rsp+88h+var_38]
0x180004c2e  mov     r13, [rsp+88h+var_28]
0x180004c33  mov     r12, [rsp+88h+var_20]
0x180004c38  mov     rbp, [rsp+88h+arg_8]
0x180004c40  test    byte ptr [rdi+1Ch], 40h
0x180004c44  jnz     short loc_180004C9C
0x180004c46  lea     rcx, [rbx+0F0h]
0x180004c4d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004c53  mov     rcx, [rsp+88h+var_40]
0x180004c58  xor     rcx, rsp; StackCookie
0x180004c5b  call    __security_check_cookie
0x180004c60  add     rsp, 70h
0x180004c64  pop     rdi
0x180004c65  pop     rsi
0x180004c66  pop     rbx
0x180004c67  retn
0x180004c68  cmp     byte ptr [rdi+19h], 4
0x180004c6c  jb      loc_180004AE6
0x180004c72  mov     eax, [rbx+98h]
0x180004c78  lea     r9, [rbx+78h]
0x180004c7c  mov     rcx, [rdi+10h]
0x180004c80  mov     dword ptr [rsp+88h+var_60], eax
0x180004c84  mov     eax, [rbx+60h]
0x180004c87  mov     [rsp+88h+var_68], eax
0x180004c8b  call    WPP_SF__guid_Ld
0x180004c90  mov     rdi, cs:WPP_GLOBAL_Control
0x180004c97  jmp     loc_180004AE6
0x180004c9c  cmp     byte ptr [rdi+19h], 4
0x180004ca0  jb      short loc_180004C46
0x180004ca2  mov     rcx, [rdi+10h]
0x180004ca6  lea     r9, [rbx+78h]
0x180004caa  mov     edx, 45h ; 'E'
0x180004caf  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004cb6  call    WPP_SF__guid_
0x180004cbb  jmp     short loc_180004C46
0x180004cbd  test    byte ptr [rdi+1Ch], 40h
0x180004cc1  jnz     loc_180004E20
0x180004cc7  mov     rax, [rbx+100h]
0x180004cce  test    rax, rax
0x180004cd1  jz      short loc_180004CDF
0x180004cd3  mov     rdx, [rax]; Buf2
0x180004cd6  test    rdx, rdx
0x180004cd9  jnz     loc_180004F98
0x180004cdf  mov     ebp, 1
0x180004ce4  test    byte ptr [rdi+1Ch], 40h
0x180004ce8  jnz     loc_180005042
0x180004cee  test    ebp, ebp
0x180004cf0  jnz     loc_180004E56
0x180004cf6  test    byte ptr [rdi+1Ch], 40h
0x180004cfa  jz      loc_180004C24
0x180004d00  cmp     byte ptr [rdi+19h], 4
0x180004d04  jb      loc_180004C24
0x180004d0a  mov     eax, [rbx+74h]
0x180004d0d  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004d14  mov     r9d, [rbx+70h]
0x180004d18  mov     edx, 41h ; 'A'
0x180004d1d  mov     rcx, [rdi+10h]
0x180004d21  mov     [rsp+88h+var_68], eax
0x180004d25  call    WPP_SF_DD
0x180004d2a  jmp     loc_180004C1D
0x180004d2f  test    byte ptr [rdi+1Ch], 40h
0x180004d33  jz      loc_180004C24
0x180004d39  cmp     byte ptr [rdi+19h], 2
0x180004d3d  jb      loc_180004C24
0x180004d43  mov     rcx, [rdi+10h]
0x180004d47  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004d4e  mov     edx, 3Ch ; '<'
0x180004d53  call    WPP_SF_
0x180004d58  jmp     loc_180004C1D
0x180004d5d  cmp     eax, 4
0x180004d60  jz      loc_180004BE1
0x180004d66  cmp     dword ptr [rbx+9Ch], 0
0x180004d6d  jnz     loc_18000516C
0x180004d73  mov     rdx, [rbx+90h]
0x180004d7a  lea     r9, [rsp+88h+var_50]
0x180004d7f  mov     rcx, [rbx+88h]
0x180004d86  xor     r8d, r8d
0x180004d89  mov     [rsp+88h+var_60], r13
0x180004d8e  mov     [rsp+88h+var_68], r15d
0x180004d93  call    cs:__imp_BrSignalBrokerEvent2
0x180004d99  test    eax, eax
0x180004d9b  js      loc_180005178
0x180004da1  cmp     dword ptr [rbx+9Ch], 0
0x180004da8  lea     rcx, [rbx+98h]
0x180004daf  jnz     loc_1800051B1
0x180004db5  mov     qword ptr [rbx+0C8h], 0
0x180004dc0  mov     dword ptr [rbx+98h], 1
0x180004dca  call    cs:__imp_RtlWakeAddressAll
0x180004dd0  jmp     loc_180004C1D
0x180004dd5  dec     eax
0x180004dd7  cmp     eax, 2
0x180004dda  ja      def_1800050DB; jumptable 00000001800050DB default case
0x180004de0  mov     ecx, [rbx+0D0h]
0x180004de6  sub     ecx, 1
0x180004de9  jz      loc_18000511D; jumptable 00000001800050DB case 1
0x180004def  cmp     ecx, 1
0x180004df2  jnz     def_1800050DB; jumptable 00000001800050DB default case
0x180004df8  cmp     [rbx+0F8h], r12d; jumptable 00000001800050DB case 2
0x180004dff  setnz   bpl
0x180004e03  jmp     def_1800050DB; jumptable 00000001800050DB default case
0x180004e08  cmp     eax, 3
0x180004e0b  jnz     loc_180004BD5
0x180004e11  cmp     bpl, 1
0x180004e15  jz      loc_180004C24
0x180004e1b  jmp     loc_180004BD5
0x180004e20  cmp     byte ptr [rdi+19h], 4
0x180004e24  jb      loc_180004CC7
0x180004e2a  mov     eax, [rbx+74h]
0x180004e2d  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004e34  mov     r9d, [rbx+70h]
0x180004e38  mov     edx, 55h ; 'U'
0x180004e3d  mov     rcx, [rdi+10h]
0x180004e41  mov     [rsp+88h+var_68], eax
0x180004e45  call    WPP_SF_DD
0x180004e4a  mov     rdi, cs:WPP_GLOBAL_Control
0x180004e51  jmp     loc_180004CC7
0x180004e56  xor     bpl, bpl
0x180004e59  test    r15d, r15d
0x180004e5c  jz      short loc_180004E6A
0x180004e5e  movups  xmm0, xmmword ptr cs:?CLSID_CustomSystemTriggerDataFactory@CBroker@@3U_GUID@@B.Data1; _GUID const CBroker::CLSID_CustomSystemTriggerDataFactory ...
0x180004e65  movups  [rsp+88h+var_50], xmm0
0x180004e6a  test    byte ptr [rdi+1Ch], 40h
0x180004e6e  jz      loc_180004BD5
0x180004e74  cmp     byte ptr [rdi+19h], 4
0x180004e78  jb      loc_180004BD5
0x180004e7e  mov     eax, [rbx+74h]
0x180004e81  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004e88  mov     r9d, [rbx+70h]
0x180004e8c  mov     edx, 42h ; 'B'
0x180004e91  mov     rcx, [rdi+10h]
0x180004e95  mov     [rsp+88h+var_68], eax
0x180004e99  call    WPP_SF_DD
0x180004e9e  jmp     loc_180004BD5
0x180004ea3  cmp     byte ptr [rdi+19h], 4
0x180004ea7  jb      loc_180004B8A
0x180004ead  mov     eax, [rbx+74h]
0x180004eb0  mov     edx, 54h ; 'T'
0x180004eb5  mov     r9d, [rbx+70h]
0x180004eb9  mov     rcx, [rdi+10h]
0x180004ebd  mov     dword ptr [rsp+88h+var_60], ebp
0x180004ec1  mov     [rsp+88h+var_68], eax
0x180004ec5  call    WPP_SF_DDd
0x180004eca  mov     rdi, cs:WPP_GLOBAL_Control
0x180004ed1  lea     r8, __ImageBase
0x180004ed8  jmp     loc_180004B8A
0x180004edd  test    byte ptr [rdi+1Ch], 40h
0x180004ee1  jz      loc_180004C24
0x180004ee7  cmp     byte ptr [rdi+19h], 2
0x180004eeb  jb      loc_180004C24
0x180004ef1  mov     edx, 3Dh ; '='
0x180004ef6  jmp     loc_180005094
0x180004efb  mov     eax, [rbx+74h]
0x180004efe  mov     edx, 53h ; 'S'
0x180004f03  mov     r9d, [rbx+70h]
0x180004f07  mov     rcx, [rdi+10h]
0x180004f0b  mov     dword ptr [rsp+88h+var_60], r12d
0x180004f10  mov     [rsp+88h+var_68], eax
0x180004f14  call    WPP_SF_DDd
0x180004f19  mov     rdi, cs:WPP_GLOBAL_Control
0x180004f20  jmp     loc_180004B5C
0x180004f25  cmp     byte ptr [rbx+0A1h], 0
0x180004f2c  jz      loc_180004AFB
0x180004f32  test    byte ptr [rdi+1Ch], 40h
0x180004f36  jz      loc_180004C29
0x180004f3c  cmp     byte ptr [rdi+19h], 2
0x180004f40  jb      loc_180004C29
0x180004f46  mov     rcx, [rdi+10h]
0x180004f4a  lea     r9, [rbx+78h]
0x180004f4e  mov     edx, 3Bh ; ';'
0x180004f53  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004f5a  call    WPP_SF__guid_
0x180004f5f  mov     rdi, cs:WPP_GLOBAL_Control
0x180004f66  jmp     loc_180004C29
0x180004f6b  mov     rcx, [rdi+10h]
0x180004f6f  lea     r9, [rbx+78h]
0x180004f73  movzx   eax, bpl
0x180004f77  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004f7e  mov     edx, 40h ; '@'
0x180004f83  mov     [rsp+88h+var_68], eax
0x180004f87  call    WPP_SF__guid_D
0x180004f8c  mov     rdi, cs:WPP_GLOBAL_Control
0x180004f93  jmp     loc_180004BB8
0x180004f98  mov     ecx, [rax+8]
0x180004f9b  test    ecx, ecx
0x180004f9d  jz      loc_180004CDF
0x180004fa3  mov     r9d, [rax+0Ch]
0x180004fa7  xor     ebp, ebp
0x180004fa9  lea     eax, [r9+rcx]
0x180004fad  cmp     r15d, eax
0x180004fb0  jb      loc_180004CE4
0x180004fb6  mov     r8d, ecx; Size
0x180004fb9  lea     rcx, [r9+r13]; Buf1
0x180004fbd  call    memcmp_0
0x180004fc2  test    eax, eax
0x180004fc4  jz      loc_18000512D
0x180004fca  jle     loc_180005075
0x180004fd0  mov     eax, [rbx+0D0h]
0x180004fd6  cmp     eax, 3
0x180004fd9  jz      loc_180004CDF
0x180004fdf  cmp     eax, 4
0x180004fe2  jz      loc_180004CDF
0x180004fe8  jmp     loc_18000507D
0x180004fed  movsxd  rax, dword ptr [rbx+60h]
0x180004ff1  sub     rax, 1000h
0x180004ff7  lea     rcx, [rax+rax*4]
0x180004ffb  test    rva byte_180035F64[r8+rcx*8], 2
0x180005004  jnz     loc_180004B9A
0x18000500a  test    byte ptr [rdi+1Ch], 40h
0x18000500e  jz      loc_180004C24
0x180005014  cmp     byte ptr [rdi+19h], 4
  ... truncated ...
```

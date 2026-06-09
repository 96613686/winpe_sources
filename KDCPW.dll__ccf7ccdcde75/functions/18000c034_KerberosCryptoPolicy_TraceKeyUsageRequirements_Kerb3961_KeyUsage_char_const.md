# KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)

- ea: `0x18000c034`
- end: `0x18000c2f5`
- name: `?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000bf24`

## callees

- `0x18000935c`
- `0x180009384`
- `0x18000940c`
- `0x18000c034`
- `0x18000c2fc`
- `0x18000d010`

## string_xrefs

- `0x18000c16a`: `KerberosCryptoPolicy::OpenEncryptionAlgorithm`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::TraceKeyUsageRequirements(_BYTE *a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 result; // rax
  __int64 v5; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  _BYTE v9[3]; // [rsp+30h] [rbp-18h] BYREF
  char v10; // [rsp+33h] [rbp-15h]
  int v11; // [rsp+38h] [rbp-10h]

  v3 = a2;
  result = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)a1 + 208LL))(*(_QWORD *)a1, v9, a2);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids, v3);
    return result;
  }
  if ( !KerberosCryptoPolicy::isolatedMode && !a1[8] )
    goto LABEL_10;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    result = WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v5, v3);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
  }
  switch ( v10 )
  {
    case 0:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        return WPP_SF_Ds(v6[2], 13, v5, v3);
      return result;
    case 1:
      if ( v6 == &WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
      {
        result = WPP_SF_Ds(v6[2], 14, v5, v3);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x20) == 0 )
        return result;
      v8 = 15;
      return WPP_SF_(v6[2], v8, &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids);
    case 2:
      if ( v6 == &WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
      {
        result = WPP_SF_Ds(v6[2], 16, v5, v3);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x20) == 0 )
        return result;
      v8 = 17;
      return WPP_SF_(v6[2], v8, &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids);
    case 3:
      if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          result = WPP_SF_Ds(v6[2], 20, v5, v3);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          v7 = 21;
          return WPP_SF_s(
                   v6[2],
                   v7,
                   &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids,
                   "KerberosCryptoPolicy::OpenEncryptionAlgorithm");
        }
      }
      break;
    case 4:
      if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          result = WPP_SF_Ds(v6[2], 18, v5, v3);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          v7 = 19;
          return WPP_SF_s(
                   v6[2],
                   v7,
                   &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids,
                   "KerberosCryptoPolicy::OpenEncryptionAlgorithm");
        }
      }
      break;
    case 5:
      if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          result = WPP_SF_Ds(v6[2], 22, v5, v3);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          v7 = 23;
          return WPP_SF_s(
                   v6[2],
                   v7,
                   &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids,
                   "KerberosCryptoPolicy::OpenEncryptionAlgorithm");
        }
      }
      break;
    default:
      if ( v10 == 6 && v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          result = WPP_SF_Ds(v6[2], 24, v5, v3);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          v7 = 25;
          return WPP_SF_s(
                   v6[2],
                   v7,
                   &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids,
                   "KerberosCryptoPolicy::OpenEncryptionAlgorithm");
        }
      }
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18000c034  mov     [rsp+arg_0], rbx
0x18000c039  mov     [rsp+arg_8], rsi
0x18000c03e  push    rdi
0x18000c03f  sub     rsp, 40h
0x18000c043  mov     rsi, rcx
0x18000c046  mov     rdi, rdx
0x18000c049  mov     rcx, [rcx]
0x18000c04c  mov     r8, rdx
0x18000c04f  lea     rdx, [rsp+48h+var_18]
0x18000c054  mov     rax, [rcx]
0x18000c057  mov     rax, [rax+0D0h]
0x18000c05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c063  cmp     [rsp+48h+var_10], 0
0x18000c068  jge     short loc_18000C0A8
0x18000c06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c071  lea     rbx, WPP_GLOBAL_Control
0x18000c078  cmp     rcx, rbx
0x18000c07b  jz      loc_18000C2E5
0x18000c081  test    byte ptr [rcx+1Ch], 1
0x18000c085  jz      loc_18000C2E5
0x18000c08b  mov     rcx, [rcx+10h]
0x18000c08f  lea     r8, WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids
0x18000c096  mov     r9d, edi
0x18000c099  mov     edx, 0Ah
0x18000c09e  call    WPP_SF_D
0x18000c0a3  jmp     loc_18000C2E5
0x18000c0a8  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x18000c0af  lea     rbx, WPP_GLOBAL_Control
0x18000c0b6  jnz     short loc_18000C0BE
0x18000c0b8  cmp     byte ptr [rsi+8], 0
0x18000c0bc  jz      short loc_18000C0E1
0x18000c0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0c5  cmp     rcx, rbx
0x18000c0c8  jz      short loc_18000C0E8
0x18000c0ca  test    byte ptr [rcx+1Ch], 1
0x18000c0ce  jz      short loc_18000C0E8
0x18000c0d0  mov     rcx, [rcx+10h]
0x18000c0d4  mov     r9d, edi
0x18000c0d7  mov     edx, 0Ch
0x18000c0dc  call    WPP_SF_Ds
0x18000c0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0e8  movzx   edx, [rsp+48h+var_15]
0x18000c0ed  test    edx, edx
0x18000c0ef  jz      loc_18000C2C9
0x18000c0f5  sub     edx, 1
0x18000c0f8  jz      loc_18000C284
0x18000c0fe  sub     edx, 1
0x18000c101  jz      loc_18000C24B
0x18000c107  sub     edx, 1
0x18000c10a  jz      loc_18000C207
0x18000c110  sub     edx, 1
0x18000c113  jz      loc_18000C1C3
0x18000c119  sub     edx, 1
0x18000c11c  jz      short loc_18000C182
0x18000c11e  cmp     edx, 1
0x18000c121  jnz     loc_18000C2E5
0x18000c127  cmp     rcx, rbx
0x18000c12a  jz      loc_18000C2E5
0x18000c130  test    byte ptr [rcx+1Ch], 20h
0x18000c134  jz      short loc_18000C14E
0x18000c136  mov     rcx, [rcx+10h]
0x18000c13a  mov     r9d, edi
0x18000c13d  mov     edx, 18h
0x18000c142  call    WPP_SF_Ds
0x18000c147  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c14e  cmp     rcx, rbx
0x18000c151  jz      loc_18000C2E5
0x18000c157  test    byte ptr [rcx+1Ch], 20h
0x18000c15b  jz      loc_18000C2E5
0x18000c161  mov     edx, 19h
0x18000c166  mov     rcx, [rcx+10h]
0x18000c16a  lea     r9, aKerberoscrypto; "KerberosCryptoPolicy::OpenEncryptionAlg"...
0x18000c171  lea     r8, WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids
0x18000c178  call    WPP_SF_s
0x18000c17d  jmp     loc_18000C2E5
0x18000c182  cmp     rcx, rbx
0x18000c185  jz      loc_18000C2E5
0x18000c18b  test    byte ptr [rcx+1Ch], 20h
0x18000c18f  jz      short loc_18000C1A9
0x18000c191  mov     rcx, [rcx+10h]
0x18000c195  mov     r9d, edi
0x18000c198  mov     edx, 16h
0x18000c19d  call    WPP_SF_Ds
0x18000c1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1a9  cmp     rcx, rbx
0x18000c1ac  jz      loc_18000C2E5
0x18000c1b2  test    byte ptr [rcx+1Ch], 20h
0x18000c1b6  jz      loc_18000C2E5
0x18000c1bc  mov     edx, 17h
0x18000c1c1  jmp     short loc_18000C166
0x18000c1c3  cmp     rcx, rbx
0x18000c1c6  jz      loc_18000C2E5
0x18000c1cc  test    byte ptr [rcx+1Ch], 20h
0x18000c1d0  jz      short loc_18000C1EA
0x18000c1d2  mov     rcx, [rcx+10h]
0x18000c1d6  mov     r9d, edi
0x18000c1d9  mov     edx, 12h
0x18000c1de  call    WPP_SF_Ds
0x18000c1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1ea  cmp     rcx, rbx
0x18000c1ed  jz      loc_18000C2E5
0x18000c1f3  test    byte ptr [rcx+1Ch], 20h
0x18000c1f7  jz      loc_18000C2E5
0x18000c1fd  mov     edx, 13h
0x18000c202  jmp     loc_18000C166
0x18000c207  cmp     rcx, rbx
0x18000c20a  jz      loc_18000C2E5
0x18000c210  test    byte ptr [rcx+1Ch], 20h
0x18000c214  jz      short loc_18000C22E
0x18000c216  mov     rcx, [rcx+10h]
0x18000c21a  mov     r9d, edi
0x18000c21d  mov     edx, 14h
0x18000c222  call    WPP_SF_Ds
0x18000c227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22e  cmp     rcx, rbx
0x18000c231  jz      loc_18000C2E5
0x18000c237  test    byte ptr [rcx+1Ch], 20h
0x18000c23b  jz      loc_18000C2E5
0x18000c241  mov     edx, 15h
0x18000c246  jmp     loc_18000C166
0x18000c24b  cmp     rcx, rbx
0x18000c24e  jz      loc_18000C2E5
0x18000c254  test    byte ptr [rcx+1Ch], 20h
0x18000c258  jz      short loc_18000C272
0x18000c25a  mov     rcx, [rcx+10h]
0x18000c25e  mov     r9d, edi
0x18000c261  mov     edx, 10h
0x18000c266  call    WPP_SF_Ds
0x18000c26b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c272  cmp     rcx, rbx
0x18000c275  jz      short loc_18000C2E5
0x18000c277  test    byte ptr [rcx+1Ch], 20h
0x18000c27b  jz      short loc_18000C2E5
0x18000c27d  mov     edx, 11h
0x18000c282  jmp     short loc_18000C2B7
0x18000c284  cmp     rcx, rbx
0x18000c287  jz      short loc_18000C2E5
0x18000c289  test    byte ptr [rcx+1Ch], 20h
0x18000c28d  jz      short loc_18000C2A7
0x18000c28f  mov     rcx, [rcx+10h]
0x18000c293  mov     r9d, edi
0x18000c296  mov     edx, 0Eh
0x18000c29b  call    WPP_SF_Ds
0x18000c2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2a7  cmp     rcx, rbx
0x18000c2aa  jz      short loc_18000C2E5
0x18000c2ac  test    byte ptr [rcx+1Ch], 20h
0x18000c2b0  jz      short loc_18000C2E5
0x18000c2b2  mov     edx, 0Fh
0x18000c2b7  mov     rcx, [rcx+10h]
0x18000c2bb  lea     r8, WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids
0x18000c2c2  call    WPP_SF_
0x18000c2c7  jmp     short loc_18000C2E5
0x18000c2c9  cmp     rcx, rbx
0x18000c2cc  jz      short loc_18000C2E5
0x18000c2ce  test    byte ptr [rcx+1Ch], 20h
0x18000c2d2  jz      short loc_18000C2E5
0x18000c2d4  mov     rcx, [rcx+10h]
0x18000c2d8  mov     r9d, edi
0x18000c2db  mov     edx, 0Dh
0x18000c2e0  call    WPP_SF_Ds
0x18000c2e5  mov     rbx, [rsp+48h+arg_0]
0x18000c2ea  mov     rsi, [rsp+48h+arg_8]
0x18000c2ef  add     rsp, 40h
0x18000c2f3  pop     rdi
0x18000c2f4  retn
```

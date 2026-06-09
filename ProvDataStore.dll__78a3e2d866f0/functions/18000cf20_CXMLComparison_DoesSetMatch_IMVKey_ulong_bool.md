# CXMLComparison::DoesSetMatch(IMVKey * *,ulong,bool *)

- ea: `0x18000cf20`
- end: `0x18000d13f`
- name: `?DoesSetMatch@CXMLComparison@@UEAAJPEAPEAUIMVKey@@KPEA_N@Z`
- size: `543`
- prototype: `__int64 __fastcall(CXMLComparison *__hidden this, struct IMVKey **, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cd94`
- `0x18000cf20`
- `0x18000da1c`
- `0x18000f2fc`
- `0x180010d44`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000cfb5`
- `msvcrt!_wcsicmp` at `0x18000cfdd`
- `msvcrt!_wcsicmp` at `0x18000cffd`
- `msvcrt!_wcsicmp` at `0x18000d01b`
- `msvcrt!_wcsicmp` at `0x18000cfb5`
- `msvcrt!_wcsicmp` at `0x18000cfdd`
- `msvcrt!_wcsicmp` at `0x18000cffd`
- `msvcrt!_wcsicmp` at `0x18000d01b`

## pseudocode

```c
__int64 __fastcall CXMLComparison::DoesSetMatch(CXMLComparison *this, struct IMVKey **a2, unsigned int a3, bool *a4)
{
  int v4; // esi
  int v5; // edi
  CXMLComparison *i; // rbx
  __int64 j; // rbp
  int DoesKeyMatchCurrentXmlAttribute; // eax
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rsi
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rdx
  char v17; // cl
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v22[14]; // [rsp+20h] [rbp-38h] BYREF
  int v23; // [rsp+60h] [rbp+8h] BYREF

  v4 = 1;
  v22[0] = 0;
  v5 = 0;
  v23 = 1;
  *((_DWORD *)this + 27) = 0;
  for ( i = this; ; this = i )
  {
    LODWORD(v12) = CXMLComparison::GetNextMatchComparison(this, (const unsigned __int16 **)&off_180019080, 7u, v22);
    if ( (int)v12 < 0 )
      break;
    if ( v22[0] )
    {
      *a4 = 1;
      if ( !*((_DWORD *)i + 23) )
      {
LABEL_37:
        LODWORD(v12) = 0;
        return (unsigned int)v12;
      }
      v12 = (unsigned int)CXMLComparison::SaveMVKeys(i, a2, a3);
      if ( v5 )
      {
        v18 = v5 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              if ( v20 == 5 )
              {
                *((_DWORD *)i + 20) = 20;
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v12);
                LODWORD(v12) = -2147418113;
              }
            }
            else
            {
              *((_DWORD *)i + 20) = 0;
            }
          }
          else
          {
            *((_DWORD *)i + 20) = 10;
          }
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v12);
          LODWORD(v12) = -2147024809;
        }
      }
      else
      {
        *((_DWORD *)i + 20) = 100;
      }
      return (unsigned int)v12;
    }
    for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
    {
      DoesKeyMatchCurrentXmlAttribute = CXMLComparison::DoesKeyMatchCurrentXmlAttribute(
                                          (__int64)i,
                                          (__int64 *)a2[j],
                                          3,
                                          &v23);
      v12 = (unsigned int)DoesKeyMatchCurrentXmlAttribute;
      if ( DoesKeyMatchCurrentXmlAttribute < 0 )
        return (unsigned int)v12;
      v4 = v23;
      if ( v23 == 2 )
      {
        v13 = (const wchar_t *)((char *)i + 48);
        if ( *((_QWORD *)i + 9) >= 8u )
          v13 = *(const wchar_t **)v13;
        if ( _wcsicmp(L"*", v13) )
          goto LABEL_37;
        v14 = (const wchar_t *)((char *)i + 16);
        if ( *((_QWORD *)i + 5) < 8u )
          v15 = (const wchar_t *)((char *)i + 16);
        else
          v15 = *(const wchar_t **)v14;
        if ( !_wcsicmp(L"mcc", v15) )
        {
          v5 |= 1u;
          *((_DWORD *)i + 21) |= 1u;
          goto LABEL_28;
        }
        if ( *((_QWORD *)i + 5) < 8u )
          v16 = (const wchar_t *)((char *)i + 16);
        else
          v16 = *(const wchar_t **)v14;
        if ( !_wcsicmp(L"mnc", v16) )
        {
          v5 |= 2u;
          *((_DWORD *)i + 21) |= 2u;
LABEL_28:
          v4 = 3;
          v23 = 3;
LABEL_29:
          v17 = 31;
          if ( a3 - (unsigned int)j - 1 < 0x1F )
            v17 = a3 - j - 1;
          *((_DWORD *)i + 22) |= 1 << v17;
          ++*((_DWORD *)i + 23);
          break;
        }
        if ( *((_QWORD *)i + 5) >= 8u )
          v14 = *(const wchar_t **)v14;
        if ( _wcsicmp(L"CarrierID", v14) )
          goto LABEL_37;
        v5 |= 8u;
        v4 = 3;
        *((_DWORD *)i + 21) |= 8u;
        v23 = 3;
      }
      if ( v4 == 3 )
        goto LABEL_29;
      if ( v4 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v12);
    }
    if ( v4 != 3 )
      goto LABEL_37;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000cf20  mov     rax, rsp
0x18000cf23  mov     [rax+10h], rbx
0x18000cf27  mov     [rax+18h], rbp
0x18000cf2b  push    rsi
0x18000cf2c  push    rdi
0x18000cf2d  push    r12
0x18000cf2f  push    r14
0x18000cf31  push    r15
0x18000cf33  sub     rsp, 30h
0x18000cf37  mov     esi, 1
0x18000cf3c  mov     dword ptr [rax-38h], 0
0x18000cf43  xor     edi, edi
0x18000cf45  mov     [rax+8], esi
0x18000cf48  mov     [rcx+6Ch], edi
0x18000cf4b  mov     r12, r9
0x18000cf4e  mov     r14d, r8d
0x18000cf51  mov     r15, rdx
0x18000cf54  mov     rbx, rcx
0x18000cf57  jmp     loc_18000D092
0x18000cf5c  cmp     [rsp+58h+var_38], 0
0x18000cf61  jnz     loc_18000D0B5
0x18000cf67  xor     ebp, ebp
0x18000cf69  test    r14d, r14d
0x18000cf6c  jz      loc_18000D08A
0x18000cf72  mov     rdx, [r15+rbp*8]
0x18000cf76  lea     r9, [rsp+58h+arg_0]
0x18000cf7b  mov     r8d, 3
0x18000cf81  mov     rcx, rbx
0x18000cf84  call    ?DoesKeyMatchCurrentXmlAttribute@CXMLComparison@@QEAAJPEAUIMVKey@@W4FieldsRequiredForMatch@@PEAW4MatchType@@@Z; CXMLComparison::DoesKeyMatchCurrentXmlAttribute(IMVKey *,FieldsRequiredForMatch,MatchType *)
0x18000cf89  mov     ecx, eax
0x18000cf8b  test    eax, eax
0x18000cf8d  js      loc_18000D126
0x18000cf93  mov     esi, [rsp+58h+arg_0]
0x18000cf97  cmp     esi, 2
0x18000cf9a  jnz     loc_18000D037
0x18000cfa0  cmp     qword ptr [rbx+48h], 8
0x18000cfa5  lea     rdx, [rbx+30h]
0x18000cfa9  jb      short loc_18000CFAE
0x18000cfab  mov     rdx, [rdx]; String2
0x18000cfae  lea     rcx, String1; "*"
0x18000cfb5  call    cs:__imp__wcsicmp
0x18000cfbb  test    eax, eax
0x18000cfbd  jnz     loc_18000D0C0
0x18000cfc3  cmp     qword ptr [rbx+28h], 8
0x18000cfc8  lea     rsi, [rbx+10h]
0x18000cfcc  jb      short loc_18000CFD3
0x18000cfce  mov     rdx, [rsi]
0x18000cfd1  jmp     short loc_18000CFD6
0x18000cfd3  mov     rdx, rsi; String2
0x18000cfd6  lea     rcx, ?gc_wszMCC@@3QBGB; "mcc"
0x18000cfdd  call    cs:__imp__wcsicmp
0x18000cfe3  test    eax, eax
0x18000cfe5  jz      short loc_18000D05C
0x18000cfe7  cmp     qword ptr [rbx+28h], 8
0x18000cfec  jb      short loc_18000CFF3
0x18000cfee  mov     rdx, [rsi]
0x18000cff1  jmp     short loc_18000CFF6
0x18000cff3  mov     rdx, rsi; String2
0x18000cff6  lea     rcx, ?gc_wszMNC@@3QBGB; "mnc"
0x18000cffd  call    cs:__imp__wcsicmp
0x18000d003  test    eax, eax
0x18000d005  jz      short loc_18000D053
0x18000d007  cmp     qword ptr [rbx+28h], 8
0x18000d00c  jb      short loc_18000D011
0x18000d00e  mov     rsi, [rsi]
0x18000d011  mov     rdx, rsi; String2
0x18000d014  lea     rcx, ?gc_wszCarrierID@@3QBGB; "CarrierID"
0x18000d01b  call    cs:__imp__wcsicmp
0x18000d021  test    eax, eax
0x18000d023  jnz     loc_18000D0C0
0x18000d029  or      edi, 8
0x18000d02c  lea     esi, [rax+3]
0x18000d02f  or      dword ptr [rbx+54h], 8
0x18000d033  mov     [rsp+58h+arg_0], esi
0x18000d037  cmp     esi, 3
0x18000d03a  jz      short loc_18000D06C
0x18000d03c  cmp     esi, 1
0x18000d03f  jz      short loc_18000D046
0x18000d041  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d046  inc     ebp
0x18000d048  cmp     ebp, r14d
0x18000d04b  jb      loc_18000CF72
0x18000d051  jmp     short loc_18000D08A
0x18000d053  or      edi, 2
0x18000d056  or      dword ptr [rbx+54h], 2
0x18000d05a  jmp     short loc_18000D063
0x18000d05c  or      edi, 1
0x18000d05f  or      dword ptr [rbx+54h], 1
0x18000d063  mov     esi, 3
0x18000d068  mov     [rsp+58h+arg_0], esi
0x18000d06c  mov     ecx, 1Fh
0x18000d071  mov     eax, r14d
0x18000d074  sub     eax, ebp
0x18000d076  dec     eax
0x18000d078  cmp     eax, ecx
0x18000d07a  cmovb   ecx, eax
0x18000d07d  mov     eax, 1
0x18000d082  shl     eax, cl
0x18000d084  or      [rbx+58h], eax
0x18000d087  inc     dword ptr [rbx+5Ch]
0x18000d08a  cmp     esi, 3
0x18000d08d  jnz     short loc_18000D0C0
0x18000d08f  mov     rcx, rbx; this
0x18000d092  lea     r9, [rsp+58h+var_38]; int *
0x18000d097  mov     r8d, 7; unsigned int
0x18000d09d  lea     rdx, off_180019080; unsigned __int16 **
0x18000d0a4  call    ?GetNextMatchComparison@CXMLComparison@@IEAAJPEAPEBGKPEAH@Z; CXMLComparison::GetNextMatchComparison(ushort const * *,ulong,int *)
0x18000d0a9  mov     ecx, eax
0x18000d0ab  test    eax, eax
0x18000d0ad  jns     loc_18000CF5C
0x18000d0b3  jmp     short loc_18000D126
0x18000d0b5  mov     byte ptr [r12], 1
0x18000d0ba  cmp     dword ptr [rbx+5Ch], 0
0x18000d0be  jnz     short loc_18000D0C4
0x18000d0c0  xor     ecx, ecx
0x18000d0c2  jmp     short loc_18000D126
0x18000d0c4  mov     r8d, r14d; unsigned int
0x18000d0c7  mov     rdx, r15; struct IMVKey **
0x18000d0ca  mov     rcx, rbx; this
0x18000d0cd  call    ?SaveMVKeys@CXMLComparison@@IEAAJPEAPEAUIMVKey@@K@Z; CXMLComparison::SaveMVKeys(IMVKey * *,ulong)
0x18000d0d2  mov     ecx, eax
0x18000d0d4  test    edi, edi
0x18000d0d6  jz      short loc_18000D11F
0x18000d0d8  sub     edi, 1
0x18000d0db  jz      short loc_18000D113
0x18000d0dd  sub     edi, 1
0x18000d0e0  jz      short loc_18000D10A
0x18000d0e2  sub     edi, 1
0x18000d0e5  jz      short loc_18000D101
0x18000d0e7  cmp     edi, 5
0x18000d0ea  jz      short loc_18000D0F8
0x18000d0ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d0f1  mov     ecx, 8000FFFFh
0x18000d0f6  jmp     short loc_18000D126
0x18000d0f8  mov     dword ptr [rbx+50h], 14h
0x18000d0ff  jmp     short loc_18000D126
0x18000d101  mov     dword ptr [rbx+50h], 0
0x18000d108  jmp     short loc_18000D126
0x18000d10a  mov     dword ptr [rbx+50h], 0Ah
0x18000d111  jmp     short loc_18000D126
0x18000d113  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d118  mov     ecx, 80070057h
0x18000d11d  jmp     short loc_18000D126
0x18000d11f  mov     dword ptr [rbx+50h], 64h ; 'd'
0x18000d126  mov     rbx, [rsp+58h+arg_8]
0x18000d12b  mov     eax, ecx
0x18000d12d  mov     rbp, [rsp+58h+arg_10]
0x18000d132  add     rsp, 30h
0x18000d136  pop     r15
0x18000d138  pop     r14
0x18000d13a  pop     r12
0x18000d13c  pop     rdi
0x18000d13d  pop     rsi
0x18000d13e  retn
```

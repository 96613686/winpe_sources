# CXMLComparisonUI::DoesSetMatch(IMVKey * *,ulong,bool *)

- ea: `0x18000d150`
- end: `0x18000d41e`
- name: `?DoesSetMatch@CXMLComparisonUI@@UEAAJPEAPEAUIMVKey@@KPEA_N@Z`
- size: `718`
- prototype: `__int64 __fastcall(CXMLComparisonUI *__hidden this, struct IMVKey **, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000cd94`
- `0x18000d150`
- `0x18000d610`
- `0x18000da1c`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d1d1`
- `msvcrt!_wcsicmp` at `0x18000d1f9`
- `msvcrt!_wcsicmp` at `0x18000d21f`
- `msvcrt!_wcsicmp` at `0x18000d245`
- `msvcrt!_wcsicmp` at `0x18000d26b`
- `msvcrt!_wcsicmp` at `0x18000d30a`
- `msvcrt!_wcsicmp` at `0x18000d1d1`
- `msvcrt!_wcsicmp` at `0x18000d1f9`
- `msvcrt!_wcsicmp` at `0x18000d21f`
- `msvcrt!_wcsicmp` at `0x18000d245`
- `msvcrt!_wcsicmp` at `0x18000d26b`
- `msvcrt!_wcsicmp` at `0x18000d30a`
- `DMCmnUtils!SafeStringToDword` at `0x18000d3e8`
- `DMCmnUtils!SafeStringToDword` at `0x18000d3e8`

## pseudocode

```c
__int64 __fastcall CXMLComparisonUI::DoesSetMatch(
        CXMLComparisonUI *this,
        struct IMVKey **a2,
        unsigned int a3,
        bool *a4)
{
  int v8; // r14d
  int NextMatchComparison; // edi
  const wchar_t *v10; // rsi
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rdx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rdx
  __int64 v16; // rbp
  char v17; // cl
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v23; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+28h] [rbp-50h] BYREF
  int v25; // [rsp+80h] [rbp+8h] BYREF

  v25 = 0;
  v23 = 1;
  *((_DWORD *)this + 29) = 1;
  *((_DWORD *)this + 27) = 0;
  v8 = 1;
  NextMatchComparison = CXMLComparison::GetNextMatchComparison(
                          this,
                          (const unsigned __int16 **)&off_180019040,
                          8u,
                          &v25);
  if ( NextMatchComparison >= 0 )
  {
    while ( 1 )
    {
      if ( v25 )
      {
        if ( *((_DWORD *)this + 23) )
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 1) + 80LL))(
                  *((_QWORD *)this + 1),
                  L"uiname",
                  0);
          NextMatchComparison = v19;
          if ( v19 >= 0 && v19 != 1 )
          {
            v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 1) + 80LL))(
                    *((_QWORD *)this + 1),
                    L"uiorder",
                    0);
            NextMatchComparison = v20;
            if ( v20 >= 0 && v20 != 1 )
            {
              v21 = *((_QWORD *)this + 1);
              v24 = 0;
              NextMatchComparison = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, _QWORD))(*(_QWORD *)v21 + 128LL))(
                                      v21,
                                      &v24,
                                      0);
              if ( NextMatchComparison >= 0 )
              {
                NextMatchComparison = SafeStringToDword(v24, 10, 1, (unsigned int *)this + 22);
                if ( NextMatchComparison >= 0 )
                {
                  *a4 = 1;
                  return (unsigned int)GetConfigSetColumns(*((_QWORD *)this + 1), (char *)this + 96, (char *)this + 104);
                }
              }
            }
          }
        }
        else
        {
          return (unsigned int)-2147024809;
        }
        return (unsigned int)NextMatchComparison;
      }
      v10 = (const wchar_t *)((char *)this + 16);
      v11 = *((_QWORD *)this + 5) < 8u ? (const wchar_t *)((char *)this + 16) : *(const wchar_t **)v10;
      if ( _wcsicmp(L"mcc", v11) )
      {
        v12 = *((_QWORD *)this + 5) < 8u ? (const wchar_t *)((char *)this + 16) : *(const wchar_t **)v10;
        if ( _wcsicmp(L"mnc", v12) )
        {
          v13 = *((_QWORD *)this + 5) < 8u ? (const wchar_t *)((char *)this + 16) : *(const wchar_t **)v10;
          if ( _wcsicmp(L"roaming", v13) )
          {
            v14 = *((_QWORD *)this + 5) < 8u ? (const wchar_t *)((char *)this + 16) : *(const wchar_t **)v10;
            if ( _wcsicmp(L"Imsi", v14) )
            {
              if ( *((_QWORD *)this + 5) < 8u )
                v15 = (const wchar_t *)((char *)this + 16);
              else
                v15 = *(const wchar_t **)v10;
              if ( !_wcsicmp(L"Esim_Prov", v15) )
                *((_DWORD *)this + 28) |= 0x20u;
            }
            else
            {
              *((_DWORD *)this + 28) |= 0x10u;
            }
          }
          else
          {
            *((_DWORD *)this + 28) |= 4u;
          }
        }
        else
        {
          *((_DWORD *)this + 28) |= 2u;
        }
      }
      else
      {
        *((_DWORD *)this + 28) |= 1u;
      }
      v16 = 0;
      if ( a3 )
        break;
LABEL_37:
      if ( v8 != 3 )
      {
LABEL_38:
        v18 = *((_DWORD *)this + 28) | 3;
        *((_DWORD *)this + 29) = 0;
        if ( v18 != *((_DWORD *)this + 21) )
          return (unsigned int)NextMatchComparison;
        if ( *((_QWORD *)this + 5) >= 8u )
          v10 = *(const wchar_t **)v10;
        if ( !_wcsicmp(L"DeviceType", v10) )
          return (unsigned int)NextMatchComparison;
      }
      NextMatchComparison = CXMLComparison::GetNextMatchComparison(
                              this,
                              (const unsigned __int16 **)&off_180019040,
                              8u,
                              &v25);
      if ( NextMatchComparison < 0 )
        return (unsigned int)NextMatchComparison;
    }
    while ( 1 )
    {
      NextMatchComparison = CXMLComparison::DoesKeyMatchCurrentXmlAttribute((__int64)this, (__int64 *)a2[v16], 3, &v23);
      if ( NextMatchComparison < 0 )
        break;
      v8 = v23;
      if ( v23 == 2 )
        goto LABEL_38;
      if ( v23 == 3 )
      {
        v17 = 31;
        if ( a3 - (unsigned int)v16 - 1 < 0x1F )
          v17 = a3 - v16 - 1;
        *((_DWORD *)this + 22) |= 1 << v17;
        ++*((_DWORD *)this + 23);
        goto LABEL_37;
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= a3 )
        goto LABEL_37;
    }
  }
  return (unsigned int)NextMatchComparison;
}

```

## disassembly

```asm
0x18000d150  mov     rax, rsp
0x18000d153  push    rbx
0x18000d154  push    rbp
0x18000d155  push    rsi
0x18000d156  push    rdi
0x18000d157  push    r12
0x18000d159  push    r13
0x18000d15b  push    r14
0x18000d15d  push    r15
0x18000d15f  sub     rsp, 38h
0x18000d163  mov     ebp, 1
0x18000d168  mov     dword ptr [rax+8], 0
0x18000d16f  mov     r12, r9
0x18000d172  mov     [rax-58h], ebp
0x18000d175  mov     r15d, r8d
0x18000d178  mov     [rcx+74h], ebp
0x18000d17b  mov     r13, rdx
0x18000d17e  mov     dword ptr [rcx+6Ch], 0
0x18000d185  lea     r8d, [rbp+7]; unsigned int
0x18000d189  mov     rbx, rcx
0x18000d18c  lea     r9, [rax+8]; int *
0x18000d190  mov     r14d, ebp
0x18000d193  lea     rdx, off_180019040; unsigned __int16 **
0x18000d19a  call    ?GetNextMatchComparison@CXMLComparison@@IEAAJPEAPEBGKPEAH@Z; CXMLComparison::GetNextMatchComparison(ushort const * *,ulong,int *)
0x18000d19f  mov     edi, eax
0x18000d1a1  test    eax, eax
0x18000d1a3  js      loc_18000D40B
0x18000d1a9  cmp     [rsp+78h+arg_0], 0
0x18000d1b1  jnz     loc_18000D349
0x18000d1b7  cmp     qword ptr [rbx+28h], 8
0x18000d1bc  lea     rsi, [rbx+10h]
0x18000d1c0  jb      short loc_18000D1C7
0x18000d1c2  mov     rdx, [rsi]
0x18000d1c5  jmp     short loc_18000D1CA
0x18000d1c7  mov     rdx, rsi; String2
0x18000d1ca  lea     rcx, ?gc_wszMCC@@3QBGB; "mcc"
0x18000d1d1  call    cs:__imp__wcsicmp
0x18000d1d7  test    eax, eax
0x18000d1d9  jnz     short loc_18000D1E3
0x18000d1db  or      [rbx+70h], ebp
0x18000d1de  jmp     loc_18000D279
0x18000d1e3  cmp     qword ptr [rbx+28h], 8
0x18000d1e8  jb      short loc_18000D1EF
0x18000d1ea  mov     rdx, [rsi]
0x18000d1ed  jmp     short loc_18000D1F2
0x18000d1ef  mov     rdx, rsi; String2
0x18000d1f2  lea     rcx, ?gc_wszMNC@@3QBGB; "mnc"
0x18000d1f9  call    cs:__imp__wcsicmp
0x18000d1ff  test    eax, eax
0x18000d201  jnz     short loc_18000D209
0x18000d203  or      dword ptr [rbx+70h], 2
0x18000d207  jmp     short loc_18000D279
0x18000d209  cmp     qword ptr [rbx+28h], 8
0x18000d20e  jb      short loc_18000D215
0x18000d210  mov     rdx, [rsi]
0x18000d213  jmp     short loc_18000D218
0x18000d215  mov     rdx, rsi; String2
0x18000d218  lea     rcx, ?gc_wszRoaming@@3QBGB; "roaming"
0x18000d21f  call    cs:__imp__wcsicmp
0x18000d225  test    eax, eax
0x18000d227  jnz     short loc_18000D22F
0x18000d229  or      dword ptr [rbx+70h], 4
0x18000d22d  jmp     short loc_18000D279
0x18000d22f  cmp     qword ptr [rbx+28h], 8
0x18000d234  jb      short loc_18000D23B
0x18000d236  mov     rdx, [rsi]
0x18000d239  jmp     short loc_18000D23E
0x18000d23b  mov     rdx, rsi; String2
0x18000d23e  lea     rcx, ?gc_wszImsi@@3QBGB; "Imsi"
0x18000d245  call    cs:__imp__wcsicmp
0x18000d24b  test    eax, eax
0x18000d24d  jnz     short loc_18000D255
0x18000d24f  or      dword ptr [rbx+70h], 10h
0x18000d253  jmp     short loc_18000D279
0x18000d255  cmp     qword ptr [rbx+28h], 8
0x18000d25a  jb      short loc_18000D261
0x18000d25c  mov     rdx, [rsi]
0x18000d25f  jmp     short loc_18000D264
0x18000d261  mov     rdx, rsi; String2
0x18000d264  lea     rcx, ?gc_wszEsimProv@@3QBGB; "Esim_Prov"
0x18000d26b  call    cs:__imp__wcsicmp
0x18000d271  test    eax, eax
0x18000d273  jnz     short loc_18000D279
0x18000d275  or      dword ptr [rbx+70h], 20h
0x18000d279  xor     ebp, ebp
0x18000d27b  test    r15d, r15d
0x18000d27e  jz      short loc_18000D2DA
0x18000d280  mov     rdx, [r13+rbp*8+0]
0x18000d285  lea     r9, [rsp+78h+var_58]
0x18000d28a  mov     r8d, 3
0x18000d290  mov     rcx, rbx
0x18000d293  call    ?DoesKeyMatchCurrentXmlAttribute@CXMLComparison@@QEAAJPEAUIMVKey@@W4FieldsRequiredForMatch@@PEAW4MatchType@@@Z; CXMLComparison::DoesKeyMatchCurrentXmlAttribute(IMVKey *,FieldsRequiredForMatch,MatchType *)
0x18000d298  mov     edi, eax
0x18000d29a  test    eax, eax
0x18000d29c  js      loc_18000D40B
0x18000d2a2  mov     r14d, [rsp+78h+var_58]
0x18000d2a7  cmp     r14d, 2
0x18000d2ab  jz      short loc_18000D2E0
0x18000d2ad  cmp     r14d, 3
0x18000d2b1  jz      short loc_18000D2BC
0x18000d2b3  inc     ebp
0x18000d2b5  cmp     ebp, r15d
0x18000d2b8  jb      short loc_18000D280
0x18000d2ba  jmp     short loc_18000D2DA
0x18000d2bc  mov     ecx, 1Fh
0x18000d2c1  mov     eax, r15d
0x18000d2c4  sub     eax, ebp
0x18000d2c6  dec     eax
0x18000d2c8  cmp     eax, ecx
0x18000d2ca  cmovb   ecx, eax
0x18000d2cd  mov     eax, 1
0x18000d2d2  shl     eax, cl
0x18000d2d4  or      [rbx+58h], eax
0x18000d2d7  inc     dword ptr [rbx+5Ch]
0x18000d2da  cmp     r14d, 3
0x18000d2de  jz      short loc_18000D318
0x18000d2e0  mov     eax, [rbx+70h]
0x18000d2e3  or      eax, 3
0x18000d2e6  mov     dword ptr [rbx+74h], 0
0x18000d2ed  cmp     eax, [rbx+54h]
0x18000d2f0  jnz     loc_18000D40B
0x18000d2f6  cmp     qword ptr [rbx+28h], 8
0x18000d2fb  jb      short loc_18000D300
0x18000d2fd  mov     rsi, [rsi]
0x18000d300  mov     rdx, rsi; String2
0x18000d303  lea     rcx, aDevicetype; "DeviceType"
0x18000d30a  call    cs:__imp__wcsicmp
0x18000d310  test    eax, eax
0x18000d312  jz      loc_18000D40B
0x18000d318  lea     r9, [rsp+78h+arg_0]; int *
0x18000d320  mov     r8d, 8; unsigned int
0x18000d326  lea     rdx, off_180019040; unsigned __int16 **
0x18000d32d  mov     rcx, rbx; this
0x18000d330  call    ?GetNextMatchComparison@CXMLComparison@@IEAAJPEAPEBGKPEAH@Z; CXMLComparison::GetNextMatchComparison(ushort const * *,ulong,int *)
0x18000d335  mov     edi, eax
0x18000d337  test    eax, eax
0x18000d339  js      loc_18000D40B
0x18000d33f  mov     ebp, 1
0x18000d344  jmp     loc_18000D1A9
0x18000d349  cmp     dword ptr [rbx+5Ch], 0
0x18000d34d  jnz     short loc_18000D359
0x18000d34f  mov     edi, 80070057h
0x18000d354  jmp     loc_18000D40B
0x18000d359  mov     rcx, [rbx+8]
0x18000d35d  lea     rdx, ?gc_wszUIName@@3QBGB; "uiname"
0x18000d364  xor     r8d, r8d
0x18000d367  mov     rax, [rcx]
0x18000d36a  mov     rax, [rax+50h]
0x18000d36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d373  bt      eax, 1Fh
0x18000d377  mov     edi, eax
0x18000d379  jb      loc_18000D40B
0x18000d37f  cmp     eax, ebp
0x18000d381  jz      loc_18000D40B
0x18000d387  mov     rcx, [rbx+8]
0x18000d38b  lea     rdx, ?gc_wszUIOrder@@3QBGB; "uiorder"
0x18000d392  xor     r8d, r8d
0x18000d395  mov     rax, [rcx]
0x18000d398  mov     rax, [rax+50h]
0x18000d39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a1  bt      eax, 1Fh
0x18000d3a5  mov     edi, eax
0x18000d3a7  jb      short loc_18000D40B
0x18000d3a9  cmp     eax, ebp
0x18000d3ab  jz      short loc_18000D40B
0x18000d3ad  mov     rcx, [rbx+8]
0x18000d3b1  lea     rdx, [rsp+78h+var_50]
0x18000d3b6  mov     [rsp+78h+var_50], 0
0x18000d3bf  xor     r8d, r8d
0x18000d3c2  mov     rax, [rcx]
0x18000d3c5  mov     rax, [rax+80h]
0x18000d3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d1  mov     edi, eax
0x18000d3d3  test    eax, eax
0x18000d3d5  js      short loc_18000D40B
0x18000d3d7  mov     rcx, [rsp+78h+var_50]
0x18000d3dc  lea     r9, [rbx+58h]
0x18000d3e0  mov     r8d, ebp
0x18000d3e3  mov     edx, 0Ah
0x18000d3e8  call    cs:__imp_?SafeStringToDword@@YAJPEBGHHPEAK@Z; SafeStringToDword(ushort const *,int,int,ulong *)
0x18000d3ee  mov     edi, eax
0x18000d3f0  test    eax, eax
0x18000d3f2  js      short loc_18000D40B
0x18000d3f4  mov     [r12], bpl
0x18000d3f8  lea     r8, [rbx+68h]
0x18000d3fc  mov     rcx, [rbx+8]
0x18000d400  lea     rdx, [rbx+60h]
0x18000d404  call    GetConfigSetColumns
0x18000d409  mov     edi, eax
0x18000d40b  mov     eax, edi
0x18000d40d  add     rsp, 38h
0x18000d411  pop     r15
0x18000d413  pop     r14
0x18000d415  pop     r13
0x18000d417  pop     r12
0x18000d419  pop     rdi
0x18000d41a  pop     rsi
0x18000d41b  pop     rbp
0x18000d41c  pop     rbx
0x18000d41d  retn
```

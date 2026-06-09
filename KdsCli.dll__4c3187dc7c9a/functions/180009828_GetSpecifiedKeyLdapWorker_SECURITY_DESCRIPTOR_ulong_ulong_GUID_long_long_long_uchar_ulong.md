# GetSpecifiedKeyLdapWorker(_SECURITY_DESCRIPTOR *,ulong,ulong,_GUID *,long,long,long,uchar * *,ulong *)

- ea: `0x180009828`
- end: `0x180009a0b`
- name: `?GetSpecifiedKeyLdapWorker@@YAJPEAU_SECURITY_DESCRIPTOR@@KKPEAU_GUID@@JJJPEAPEAEPEAK@Z`
- size: `483`
- prototype: `int(struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int, struct _GUID *, int, int, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009408`

## callees

- `0x180003e30`
- `0x180008eb4`
- `0x180009828`
- `0x180010010`
- `0x18001a450`

## string_xrefs

- `0x1800099b2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetSpecifiedKeyLdapWorker(
        struct _SECURITY_DESCRIPTOR *a1,
        unsigned int a2,
        ULONG a3,
        struct _GUID *a4,
        int a5,
        int a6,
        int a7,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  unsigned int v10; // r14d
  int v11; // r8d
  int v12; // ecx
  int v13; // edx
  int SIDKeyLdapWorker; // eax
  unsigned int v15; // ebx
  unsigned int v16; // r9d
  unsigned int v17; // ecx
  unsigned int v19; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+64h] [rbp-1Ch] BYREF
  unsigned int v21; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+6Ch] [rbp-14h] BYREF
  unsigned int v23; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v24[3]; // [rsp+74h] [rbp-Ch] BYREF

  v22 = 0;
  v24[0] = 0;
  v23 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( a6 > 32 || a7 > 32 )
    goto LABEL_23;
  v10 = 1;
  *a8 = 0;
  *a9 = 0;
  if ( a5 == -1 )
  {
    if ( a6 != -1 )
    {
LABEL_23:
      v15 = -2147024809;
      goto LABEL_24;
    }
    if ( a7 == -1 )
    {
      GetCurrentIntervalID(0x53D1AC1000uLL, 0, &v19, &v20, &v21);
      v11 = v19;
      v12 = v20;
      v13 = v21;
      v10 = a4 != 0;
      goto LABEL_19;
    }
  }
  if ( a5 <= 0 || a6 < 0 || a7 < 0 )
    goto LABEL_23;
  GetCurrentIntervalID(0x53D1AC1000uLL, 1, &v22, v24, &v23);
  if ( a5 > (int)v22 || (v13 = v23, v12 = v24[0], a5 == v22) && (a6 > (int)v24[0] || a6 == v24[0] && a7 > (int)v23) )
  {
    v15 = -2147024809;
    v16 = 1959;
    v17 = -2147024809;
    goto LABEL_22;
  }
  v11 = a5;
  if ( a4 )
  {
    if ( a5 < (int)v22 )
    {
      v12 = 31;
      v13 = 31;
    }
  }
  else
  {
    v13 = a7;
    v12 = a6;
    v10 = 2;
  }
LABEL_19:
  SIDKeyLdapWorker = GetSIDKeyLdapWorker(a1, a2, a3, v10, a4, v11, v12, v13, a5 == -1, a8, a9);
  v15 = SIDKeyLdapWorker;
  if ( SIDKeyLdapWorker < 0 )
  {
    v16 = 2032;
    v17 = SIDKeyLdapWorker;
LABEL_22:
    SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v16);
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_497df786d6153c614e507117de9dfe52_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180009828  mov     [rsp-38h+arg_10], r8d
0x18000982d  mov     [rsp-38h+arg_8], edx
0x180009831  mov     [rsp-38h+arg_0], rcx
0x180009836  push    rbp
0x180009837  push    rbx
0x180009838  push    rsi
0x180009839  push    r12
0x18000983b  push    r13
0x18000983d  push    r14
0x18000983f  push    r15
0x180009841  mov     rbp, rsp
0x180009844  sub     rsp, 80h
0x18000984b  mov     ebx, [rbp+arg_28]
0x18000984e  xor     eax, eax
0x180009850  mov     [rbp+var_14], eax
0x180009853  mov     r15, r9
0x180009856  mov     [rbp+var_C], eax
0x180009859  mov     [rbp+var_10], eax
0x18000985c  mov     [rbp+var_20], eax
0x18000985f  mov     [rbp+var_1C], eax
0x180009862  mov     [rbp+var_18], eax
0x180009865  cmp     ebx, 20h ; ' '
0x180009868  jg      loc_1800099C0
0x18000986e  cmp     [rbp+arg_30], 20h ; ' '
0x180009872  jg      loc_1800099C0
0x180009878  mov     r12, [rbp+arg_38]
0x18000987c  lea     r14d, [rax+1]
0x180009880  mov     r13, [rbp+arg_40]
0x180009887  mov     esi, [rbp+arg_20]
0x18000988a  mov     [r12], rax
0x18000988e  mov     [r13+0], eax
0x180009892  cmp     esi, 0FFFFFFFFh
0x180009895  jnz     short loc_1800098DA
0x180009897  cmp     ebx, esi
0x180009899  jnz     loc_1800099C0
0x18000989f  cmp     [rbp+arg_30], esi
0x1800098a2  jnz     short loc_1800098DA
0x1800098a4  lea     rax, [rbp+var_18]
0x1800098a8  xor     edx, edx; int
0x1800098aa  lea     r9, [rbp+var_1C]; unsigned int *
0x1800098ae  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800098b3  lea     r8, [rbp+var_20]; unsigned int *
0x1800098b7  mov     rcx, 53D1AC1000h; unsigned __int64
0x1800098c1  call    ?GetCurrentIntervalID@@YAX_KHPEAK11@Z; GetCurrentIntervalID(unsigned __int64,int,ulong *,ulong *,ulong *)
0x1800098c6  mov     r8d, [rbp+var_20]
0x1800098ca  mov     ecx, [rbp+var_1C]
0x1800098cd  mov     edx, [rbp+var_18]
0x1800098d0  test    r15, r15
0x1800098d3  jnz     short loc_180009950
0x1800098d5  xor     r14d, r14d
0x1800098d8  jmp     short loc_180009950
0x1800098da  test    esi, esi
0x1800098dc  jle     loc_1800099C0
0x1800098e2  test    ebx, ebx
0x1800098e4  js      loc_1800099C0
0x1800098ea  cmp     [rbp+arg_30], eax
0x1800098ed  jl      loc_1800099C0
0x1800098f3  lea     rax, [rbp+var_10]
0x1800098f7  mov     edx, r14d; int
0x1800098fa  lea     r9, [rbp+var_C]; unsigned int *
0x1800098fe  mov     [rsp+80h+var_60], rax; unsigned int *
0x180009903  lea     r8, [rbp+var_14]; unsigned int *
0x180009907  mov     rcx, 53D1AC1000h; unsigned __int64
0x180009911  call    ?GetCurrentIntervalID@@YAX_KHPEAK11@Z; GetCurrentIntervalID(unsigned __int64,int,ulong *,ulong *,ulong *)
0x180009916  mov     eax, [rbp+var_14]
0x180009919  cmp     esi, eax
0x18000991b  jg      short loc_18000999B
0x18000991d  mov     edx, [rbp+var_10]
0x180009920  mov     ecx, [rbp+var_C]
0x180009923  jnz     short loc_180009930
0x180009925  cmp     ebx, ecx
0x180009927  jg      short loc_18000999B
0x180009929  jnz     short loc_180009930
0x18000992b  cmp     [rbp+arg_30], edx
0x18000992e  jg      short loc_18000999B
0x180009930  mov     r8d, esi
0x180009933  test    r15, r15
0x180009936  jz      short loc_180009945
0x180009938  cmp     esi, eax
0x18000993a  jge     short loc_180009950
0x18000993c  mov     ecx, 1Fh
0x180009941  mov     edx, ecx
0x180009943  jmp     short loc_180009950
0x180009945  mov     edx, [rbp+arg_30]
0x180009948  mov     ecx, ebx
0x18000994a  mov     r14d, 2
0x180009950  mov     [rsp+80h+var_30], r13; unsigned int *
0x180009955  xor     eax, eax
0x180009957  mov     [rsp+80h+var_38], r12; unsigned __int8 **
0x18000995c  cmp     esi, 0FFFFFFFFh
0x18000995f  mov     r9d, r14d; unsigned int
0x180009962  setz    al
0x180009965  mov     [rsp+80h+var_40], eax; int
0x180009969  mov     [rsp+80h+var_48], edx; unsigned int
0x18000996d  mov     edx, [rbp+arg_8]; unsigned int
0x180009970  mov     [rsp+80h+var_50], ecx; unsigned int
0x180009974  mov     rcx, [rbp+arg_0]; struct _SECURITY_DESCRIPTOR *
0x180009978  mov     [rsp+80h+var_58], r8d; unsigned int
0x18000997d  mov     r8d, [rbp+arg_10]; unsigned int
0x180009981  mov     [rsp+80h+var_60], r15; struct _GUID *
0x180009986  call    ?GetSIDKeyLdapWorker@@YAJPEAU_SECURITY_DESCRIPTOR@@KKKPEAU_GUID@@KKKHPEAPEAEPEAK@Z; GetSIDKeyLdapWorker(_SECURITY_DESCRIPTOR *,ulong,ulong,ulong,_GUID *,ulong,ulong,ulong,int,uchar * *,ulong *)
0x18000998b  mov     ebx, eax
0x18000998d  test    eax, eax
0x18000998f  jns     short loc_1800099C5
0x180009991  mov     r9d, 7F0h
0x180009997  mov     ecx, eax
0x180009999  jmp     short loc_1800099AB
0x18000999b  mov     ebx, 80070057h
0x1800099a0  mov     r9d, 7A7h; unsigned int
0x1800099a6  mov     ecx, 80070057h; unsigned int
0x1800099ab  lea     rdx, aHr; "hr"
0x1800099b2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800099b9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800099be  jmp     short loc_1800099C5
0x1800099c0  mov     ebx, 80070057h
0x1800099c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099cc  lea     rax, WPP_GLOBAL_Control
0x1800099d3  cmp     rcx, rax
0x1800099d6  jz      short loc_1800099F6
0x1800099d8  test    byte ptr [rcx+1Ch], 4
0x1800099dc  jz      short loc_1800099F6
0x1800099de  mov     rcx, [rcx+10h]
0x1800099e2  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800099e9  mov     edx, 13h
0x1800099ee  mov     r9d, ebx
0x1800099f1  call    WPP_SF_D
0x1800099f6  mov     eax, ebx
0x1800099f8  add     rsp, 80h
0x1800099ff  pop     r15
0x180009a01  pop     r14
0x180009a03  pop     r13
0x180009a05  pop     r12
0x180009a07  pop     rsi
0x180009a08  pop     rbx
0x180009a09  pop     rbp
0x180009a0a  retn
```

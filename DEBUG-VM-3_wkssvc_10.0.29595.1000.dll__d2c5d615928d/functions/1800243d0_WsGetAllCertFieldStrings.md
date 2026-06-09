# WsGetAllCertFieldStrings

- ea: `0x1800243d0`
- end: `0x180024654`
- name: `WsGetAllCertFieldStrings`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180020b04`

## callees

- `0x18001c6dc`
- `0x180022b7c`
- `0x1800243d0`
- `0x18002465c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800245f6`
- `ntdll!RtlNtStatusToDosError` at `0x1800245f6`
- `ntdll!RtlUnicodeStringToInteger` at `0x180024591`
- `ntdll!RtlUnicodeStringToInteger` at `0x180024591`
- `ntdll!RtlInitUnicodeString` at `0x180024524`
- `ntdll!RtlInitUnicodeString` at `0x180024524`
- `ntdll!RtlFreeUnicodeString` at `0x18002459f`
- `ntdll!RtlFreeUnicodeString` at `0x18002459f`

## string_xrefs

- `0x1800244a7`: `StoreName`

## pseudocode

```c
__int64 __fastcall WsGetAllCertFieldStrings(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int CertFieldString; // esi
  unsigned __int16 v6; // di
  const WCHAR *v7; // r15
  __int64 v8; // rcx
  char v9; // r14
  WCHAR **v10; // r9
  __int64 v11; // rcx
  int v12; // r14d
  UNICODE_STRING String; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-C0h]
  _BYTE v17[8]; // [rsp+48h] [rbp-B8h]
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h]
  char v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  const WCHAR *v21; // [rsp+70h] [rbp-90h]
  char v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  const WCHAR *v24; // [rsp+88h] [rbp-78h]
  char v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  const WCHAR *v27; // [rsp+A0h] [rbp-60h]
  char v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  const WCHAR *v30; // [rsp+B8h] [rbp-48h]
  char v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  const WCHAR *v33; // [rsp+D0h] [rbp-30h]
  char v34; // [rsp+D8h] [rbp-28h]
  __int64 v35; // [rsp+E0h] [rbp-20h]
  const WCHAR *v36; // [rsp+E8h] [rbp-18h]
  char v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  const WCHAR *v39; // [rsp+100h] [rbp+0h]
  char v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+110h] [rbp+10h]
  const WCHAR *v42; // [rsp+118h] [rbp+18h]
  char v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  __int64 Value; // [rsp+170h] [rbp+70h] BYREF
  WCHAR *v46; // [rsp+180h] [rbp+80h] BYREF

  Value = a1;
  v3 = *a3;
  SourceString = L"Subject";
  v46 = 0;
  LODWORD(Value) = 0;
  v17[0] = 0;
  v18[0] = v3 + 8;
  CertFieldString = 0;
  v19 = 0;
  v18[1] = L"Issuer";
  v6 = 0;
  v22 = 0;
  v20 = v3 + 16;
  v21 = L"ThumbPrint";
  v23 = v3 + 24;
  v24 = L"FriendlyName";
  v26 = v3 + 32;
  v27 = L"NotBefore";
  v29 = v3 + 40;
  v30 = L"NotAfter";
  v32 = v3 + 48;
  v33 = L"StoreLocation";
  v35 = v3 + 56;
  v36 = L"StoreName";
  v38 = v3 + 64;
  v39 = L"Type";
  v41 = v3 + 80;
  v42 = L"Flags";
  v44 = v3 + 84;
  DestinationString = 0;
  v25 = 0;
  String = 0;
  v28 = 0;
  v31 = 0;
  v34 = 0;
  v37 = 0;
  v40 = 1;
  v43 = 1;
  while ( v6 < 0xAu )
  {
    v7 = *(const WCHAR **)&v17[24 * v6 - 8];
    RtlInitUnicodeString(&DestinationString, v7);
    v9 = v17[24 * v6];
    v10 = &v46;
    if ( !v9 )
      v10 = (WCHAR **)v18[3 * v6];
    CertFieldString = WsGetCertFieldString(v8, a2, &DestinationString, v10);
    if ( CertFieldString )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v7);
      }
      return CertFieldString;
    }
    if ( v9 )
    {
      v11 = -1;
      String.Buffer = v46;
      do
        ++v11;
      while ( v46[v11] );
      String.MaximumLength = 2 * (v11 + 1);
      String.Length = String.MaximumLength;
      v12 = RtlUnicodeStringToInteger(&String, 0, (PULONG)&Value);
      RtlFreeUnicodeString(&String);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
            (unsigned int)v12);
        }
        return RtlNtStatusToDosError(v12);
      }
      *(_DWORD *)v18[3 * v6] = Value;
    }
    ++v6;
  }
  return CertFieldString;
}

```

## disassembly

```asm
0x1800243d0  mov     [rsp-8+arg_8], rbx
0x1800243d5  mov     [rsp-8+Value], rcx
0x1800243da  push    rbp
0x1800243db  push    rsi
0x1800243dc  push    rdi
0x1800243dd  push    r12
0x1800243df  push    r13
0x1800243e1  push    r14
0x1800243e3  push    r15
0x1800243e5  lea     rbp, [rsp-30h]
0x1800243ea  sub     rsp, 130h
0x1800243f1  mov     rcx, [r8]
0x1800243f4  lea     rax, aSubject; "Subject"
0x1800243fb  mov     [rsp+160h+SourceString], rax
0x180024400  xor     r13d, r13d
0x180024403  xorps   xmm0, xmm0
0x180024406  mov     [rbp+60h+arg_10], r13
0x18002440d  mov     r12, rdx
0x180024410  mov     dword ptr [rbp+60h+Value], r13d
0x180024414  lea     rax, [rcx+8]
0x180024418  mov     [rsp+160h+var_118], r13b
0x18002441d  mov     [rsp+160h+var_110], rax
0x180024422  mov     esi, r13d
0x180024425  lea     rax, aIssuer; "Issuer"
0x18002442c  mov     [rsp+160h+var_100], r13b
0x180024431  mov     [rsp+160h+var_108], rax
0x180024436  mov     edi, r13d
0x180024439  lea     rax, [rcx+10h]
0x18002443d  mov     [rsp+160h+var_E8], r13b
0x180024442  mov     [rsp+160h+var_F8], rax
0x180024447  lea     rax, aThumbprint; "ThumbPrint"
0x18002444e  mov     [rsp+160h+var_F0], rax
0x180024453  lea     rax, [rcx+18h]
0x180024457  mov     [rbp+60h+var_E0], rax
0x18002445b  lea     rax, aFriendlyname; "FriendlyName"
0x180024462  mov     [rbp+60h+var_D8], rax
0x180024466  lea     rax, [rcx+20h]
0x18002446a  mov     [rbp+60h+var_C8], rax
0x18002446e  lea     rax, aNotbefore; "NotBefore"
0x180024475  mov     [rbp+60h+var_C0], rax
0x180024479  lea     rax, [rcx+28h]
0x18002447d  mov     [rbp+60h+var_B0], rax
0x180024481  lea     rax, aNotafter; "NotAfter"
0x180024488  mov     [rbp+60h+var_A8], rax
0x18002448c  lea     rax, [rcx+30h]
0x180024490  mov     [rbp+60h+var_98], rax
0x180024494  lea     rax, aStorelocation; "StoreLocation"
0x18002449b  mov     [rbp+60h+var_90], rax
0x18002449f  lea     rax, [rcx+38h]
0x1800244a3  mov     [rbp+60h+var_80], rax
0x1800244a7  lea     rax, aStorename; "StoreName"
0x1800244ae  mov     [rbp+60h+var_78], rax
0x1800244b2  lea     rax, [rcx+40h]
0x1800244b6  mov     [rbp+60h+var_68], rax
0x1800244ba  lea     rax, aType; "Type"
0x1800244c1  mov     [rbp+60h+var_60], rax
0x1800244c5  lea     rax, [rcx+50h]
0x1800244c9  mov     [rbp+60h+var_50], rax
0x1800244cd  lea     rax, aFlags; "Flags"
0x1800244d4  mov     [rbp+60h+var_48], rax
0x1800244d8  lea     rax, [rcx+54h]
0x1800244dc  mov     [rbp+60h+var_38], rax
0x1800244e0  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1800244e5  mov     [rbp+60h+var_D0], r13b
0x1800244e9  movups  xmmword ptr [rsp+160h+String.Length], xmm0
0x1800244ee  mov     [rbp+60h+var_B8], r13b
0x1800244f2  mov     [rbp+60h+var_A0], r13b
0x1800244f6  mov     [rbp+60h+var_88], r13b
0x1800244fa  mov     [rbp+60h+var_70], r13b
0x1800244fe  mov     [rbp+60h+var_58], 1
0x180024502  mov     [rbp+60h+var_40], 1
0x180024506  cmp     di, 0Ah
0x18002450a  jnb     loc_180024637
0x180024510  movzx   eax, di
0x180024513  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x180024518  lea     rbx, [rax+rax*2]
0x18002451c  mov     r15, [rsp+rbx*8+160h+SourceString]
0x180024521  mov     rdx, r15; SourceString
0x180024524  call    cs:__imp_RtlInitUnicodeString
0x18002452a  mov     r14b, [rsp+rbx*8+160h+var_118]
0x18002452f  lea     r9, [rbp+60h+arg_10]
0x180024536  test    r14b, r14b
0x180024539  jnz     short loc_180024540
0x18002453b  mov     r9, [rsp+rbx*8+160h+var_110]
0x180024540  lea     r8, [rsp+160h+DestinationString]
0x180024545  mov     rdx, r12
0x180024548  call    WsGetCertFieldString
0x18002454d  mov     esi, eax
0x18002454f  test    eax, eax
0x180024551  jnz     loc_180024600
0x180024557  test    r14b, r14b
0x18002455a  jz      short loc_1800245B4
0x18002455c  mov     rax, [rbp+60h+arg_10]
0x180024563  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024567  mov     [rsp+160h+String.Buffer], rax
0x18002456c  inc     rcx
0x18002456f  cmp     [rax+rcx*2], r13w
0x180024574  jnz     short loc_18002456C
0x180024576  inc     cx
0x180024579  lea     r8, [rbp+60h+Value]; Value
0x18002457d  add     cx, cx
0x180024580  xor     edx, edx; Base
0x180024582  mov     [rsp+160h+String.MaximumLength], cx
0x180024587  mov     [rsp+160h+String.Length], cx
0x18002458c  lea     rcx, [rsp+160h+String]; String
0x180024591  call    cs:__imp_RtlUnicodeStringToInteger
0x180024597  lea     rcx, [rsp+160h+String]; UnicodeString
0x18002459c  mov     r14d, eax
0x18002459f  call    cs:__imp_RtlFreeUnicodeString
0x1800245a5  test    r14d, r14d
0x1800245a8  js      short loc_1800245BC
0x1800245aa  mov     rcx, [rsp+rbx*8+160h+var_110]
0x1800245af  mov     eax, dword ptr [rbp+60h+Value]
0x1800245b2  mov     [rcx], eax
0x1800245b4  inc     di
0x1800245b7  jmp     loc_180024506
0x1800245bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800245c3  lea     rax, WPP_GLOBAL_Control
0x1800245ca  cmp     rcx, rax
0x1800245cd  jz      short loc_1800245F3
0x1800245cf  test    byte ptr [rcx+1Ch], 2
0x1800245d3  jz      short loc_1800245F3
0x1800245d5  cmp     byte ptr [rcx+19h], 1
0x1800245d9  jb      short loc_1800245F3
0x1800245db  mov     rcx, [rcx+10h]
0x1800245df  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800245e6  mov     edx, 0Fh
0x1800245eb  mov     r9d, r14d
0x1800245ee  call    WPP_SF_d
0x1800245f3  mov     ecx, r14d; Status
0x1800245f6  call    cs:__imp_RtlNtStatusToDosError
0x1800245fc  mov     esi, eax
0x1800245fe  jmp     short loc_180024637
0x180024600  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024607  lea     rax, WPP_GLOBAL_Control
0x18002460e  cmp     rcx, rax
0x180024611  jz      short loc_180024637
0x180024613  test    byte ptr [rcx+1Ch], 2
0x180024617  jz      short loc_180024637
0x180024619  cmp     byte ptr [rcx+19h], 1
0x18002461d  jb      short loc_180024637
0x18002461f  mov     rcx, [rcx+10h]
0x180024623  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002462a  mov     edx, 0Eh
0x18002462f  mov     r9, r15
0x180024632  call    WPP_SF_S
0x180024637  mov     rbx, [rsp+160h+arg_8]
0x18002463f  mov     eax, esi
0x180024641  add     rsp, 130h
0x180024648  pop     r15
0x18002464a  pop     r14
0x18002464c  pop     r13
0x18002464e  pop     r12
0x180024650  pop     rdi
0x180024651  pop     rsi
0x180024652  pop     rbp
0x180024653  retn
```

# GetVolumeDeviceInPath

- ea: `0x18004e358`
- end: `0x18004eacb`
- name: `GetVolumeDeviceInPath`
- size: `1907`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004dc58`
- `0x18004ead4`

## callees

- `0x18004e358`
- `0x180050198`
- `0x180050300`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x18004e442`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e609`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e654`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e69f`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e6ea`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e7b5`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e83b`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e922`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ea94`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e442`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e609`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e654`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e69f`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e6ea`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e7b5`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e83b`
- `ntdll!RtlPrefixUnicodeString` at `0x18004e922`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ea94`
- `ntdll!RtlGUIDFromString` at `0x18004e8df`
- `ntdll!RtlGUIDFromString` at `0x18004e8df`

## string_xrefs

- `0x18004e3aa`: `\Device\HarddiskVolumeShadowCopy`

## pseudocode

```c
__int64 __fastcall GetVolumeDeviceInPath(PCUNICODE_STRING String2, __int64 a2, __int64 a3)
{
  USHORT i; // bx
  PWSTR v7; // r8
  USHORT v8; // cx
  USHORT v9; // dx
  unsigned __int64 v10; // r9
  WCHAR v11; // cx
  USHORT v12; // dx
  WCHAR v13; // cx
  WCHAR v14; // cx
  USHORT v15; // dx
  PWSTR Buffer; // rdx
  WCHAR v17; // cx
  __int64 v18; // r9
  int v19; // ecx
  PWSTR v20; // rax
  GUID v21; // xmm0
  WCHAR *v22; // rcx
  USHORT v23; // ax
  PWSTR v24; // rdx
  __int64 v25; // r9
  int v26; // r8d
  unsigned __int64 Length; // r9
  PWSTR v28; // r8
  unsigned __int64 v29; // rcx
  WCHAR v30; // r10
  unsigned __int16 v31; // dx
  unsigned __int16 v32; // dx
  unsigned __int64 v33; // rcx
  __int16 v34; // ax
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-89h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING v38; // [rsp+40h] [rbp-69h] BYREF
  UNICODE_STRING v39; // [rsp+50h] [rbp-59h] BYREF
  UNICODE_STRING v40; // [rsp+60h] [rbp-49h] BYREF
  UNICODE_STRING v41; // [rsp+70h] [rbp-39h] BYREF
  UNICODE_STRING v42; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING v43; // [rsp+90h] [rbp-19h] BYREF
  UNICODE_STRING v44; // [rsp+A0h] [rbp-9h] BYREF
  UNICODE_STRING v45; // [rsp+B0h] [rbp+7h] BYREF
  GUID Guid; // [rsp+C0h] [rbp+17h] BYREF

  *(_QWORD *)&v45.Length = 1179664;
  v45.Buffer = L"\\Device\\";
  *(_QWORD *)&String1.Length = 1572886;
  String1.Buffer = L"\\Device\\Mup";
  *(_QWORD *)&v38.Length = 4325440;
  v38.Buffer = L"\\Device\\HarddiskVolumeShadowCopy";
  *(_QWORD *)&v39.Length = 3014700;
  v39.Buffer = L"\\Device\\HarddiskVolume";
  *(_QWORD *)&v40.Length = 1835034;
  v40.Buffer = L"\\Device\\CdRom";
  *(_QWORD *)&v41.Length = 2228256;
  v41.Buffer = L"\\Device\\Harddisk";
  *(_QWORD *)&v42.Length = 1966108;
  v42.Buffer = L"\\Device\\Volume";
  *(_QWORD *)&v43.Length = 2097182;
  v43.Buffer = L"\\Device\\Ramdisk";
  v44.Buffer = L"\\Device\\RdpDr";
  *(_QWORD *)&v44.Length = 1835034;
  if ( !RtlPrefixUnicodeString(&String1, String2, 1u) )
  {
    if ( RtlPrefixUnicodeString(&v38, String2, 1u) )
    {
      for ( i = v38.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v39, String2, 1u) )
    {
      for ( i = v39.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v40, String2, 1u) )
    {
      for ( i = v40.Length; i < String2->Length; i += 2 )
      {
        if ( (unsigned __int16)(String2->Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
      }
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v41, String2, 1u) )
    {
      i = v41.Length;
      if ( v41.Length >= String2->Length )
        return 3221225659LL;
      Buffer = String2->Buffer;
      while ( (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) <= 9u )
      {
        i += 2;
        if ( i >= String2->Length )
          return 3221225659LL;
      }
      if ( Buffer[(unsigned __int64)i >> 1] != 92 )
        return 3221225659LL;
      do
      {
        i += 2;
        if ( i >= String2->Length )
          break;
        v17 = Buffer[(unsigned __int64)i >> 1];
      }
      while ( (unsigned __int16)(v17 - 97) <= 0x19u || (unsigned __int16)(v17 - 65) <= 0x19u );
      if ( i >= String2->Length || (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
        return 3221225659LL;
      do
      {
        if ( (unsigned __int16)(Buffer[(unsigned __int64)i >> 1] - 48) > 9u )
          break;
        i += 2;
      }
      while ( i < String2->Length );
      goto LABEL_115;
    }
    if ( RtlPrefixUnicodeString(&v42, String2, 1u) )
    {
      i = v42.Length;
      if ( v42.Length < String2->Length )
      {
        v18 = 0x3FFFFFF01FF9LL;
        do
        {
          v19 = String2->Buffer[(unsigned __int64)i >> 1];
          if ( (unsigned __int16)(v19 - 97) > 0x1Au
            && ((unsigned __int16)(v19 - 45) > 0x2Du || !_bittest64(&v18, (unsigned int)(v19 - 45)))
            && (_WORD)v19 != 125 )
          {
            break;
          }
          i += 2;
        }
        while ( i < String2->Length );
      }
      v20 = String2->Buffer;
      v21 = 0;
      *(_QWORD *)&GuidString.Length = 0;
      v22 = &v20[(unsigned __int64)v42.Length >> 1];
      v23 = i - v42.Length;
      GuidString.Buffer = v22;
    }
    else
    {
      if ( !RtlPrefixUnicodeString(&v43, String2, 1u) )
      {
        if ( RtlPrefixUnicodeString(&v44, String2, 1u) )
        {
          Length = String2->Length;
          if ( (unsigned __int64)v44.Length + 8 < Length )
          {
            v28 = String2->Buffer;
            v29 = (unsigned __int64)v44.Length >> 1;
            if ( v28[v29] == 92 && v28[v29 + 1] == 59 )
            {
              v30 = v28[v29 + 2];
              if ( ((unsigned __int16)(v30 - 97) <= 0x19u || (unsigned __int16)(v30 - 65) <= 0x19u)
                && v28[v29 + 3] == 58 )
              {
                v31 = v44.Length + 8;
                if ( (unsigned __int16)(v44.Length + 8) < (unsigned __int16)Length
                  && (unsigned __int16)(v28[(unsigned __int64)v31 >> 1] - 48) <= 9u )
                {
                  while ( 1 )
                  {
                    v31 += 2;
                    if ( v31 >= (unsigned __int16)Length )
                      break;
                    if ( (unsigned __int16)(v28[(unsigned __int64)v31 >> 1] - 48) > 9u )
                    {
                      if ( v28[(unsigned __int64)v31 >> 1] != 92 )
                        return 3221225659LL;
                      v32 = v31 + 2;
                      if ( v32 >= (unsigned __int16)Length )
                        return 3221225659LL;
                      while ( 1 )
                      {
                        i = v32 + 2;
                        if ( v28[(unsigned __int64)v32 >> 1] == 92 )
                          break;
                        v32 += 2;
                        if ( i >= (unsigned __int16)Length )
                          return 3221225659LL;
                      }
                      while ( i < (unsigned __int16)Length && v28[(unsigned __int64)i >> 1] != 92 )
                        i += 2;
                      goto LABEL_115;
                    }
                  }
                }
              }
            }
          }
        }
        else if ( RtlPrefixUnicodeString(&v45, String2, 1u) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        return 3221225659LL;
      }
      i = v43.Length;
      if ( v43.Length >= String2->Length )
        goto LABEL_115;
      v24 = String2->Buffer;
      if ( v24[(unsigned __int64)v43.Length >> 1] != 123 )
      {
        do
        {
          if ( (unsigned __int16)(v24[(unsigned __int64)i >> 1] - 48) > 9u )
            break;
          i += 2;
        }
        while ( i < String2->Length );
        goto LABEL_115;
      }
      v25 = 0x3FFFFFF01FF9LL;
      do
      {
        v26 = v24[(unsigned __int64)i >> 1];
        if ( (unsigned __int16)(v26 - 97) > 0x1Au
          && ((unsigned __int16)(v26 - 45) > 0x2Du || !_bittest64(&v25, (unsigned int)(v26 - 45)))
          && (_WORD)v26 != 125 )
        {
          break;
        }
        i += 2;
      }
      while ( i < String2->Length );
      v21 = 0;
      *(_QWORD *)&GuidString.Length = 0;
      GuidString.Buffer = &v24[(unsigned __int64)v43.Length >> 1];
      v23 = i - v43.Length;
    }
    GuidString.MaximumLength = v23;
    GuidString.Length = v23;
    Guid = v21;
    if ( RtlGUIDFromString(&GuidString, &Guid) >= 0 )
      goto LABEL_115;
    return 3221225659LL;
  }
  i = String1.Length;
  if ( String1.Length >= String2->Length )
  {
    if ( String1.Length == String2->Length )
      goto LABEL_115;
    return 3221225659LL;
  }
  v7 = String2->Buffer;
  if ( v7[(unsigned __int64)String1.Length >> 1] != 92 )
    return 3221225659LL;
  v8 = String1.Length + 2;
  if ( (unsigned __int16)(String1.Length + 2) < String2->Length )
  {
    if ( v7[(unsigned __int64)v8 >> 1] == 59 )
    {
      do
        v8 += 2;
      while ( v8 < String2->Length && v7[(unsigned __int64)v8 >> 1] != 92 );
      i = v8;
    }
    else if ( v8 < String2->Length )
    {
      while ( 1 )
      {
        v9 = v8 + 2;
        if ( v7[(unsigned __int64)v8 >> 1] == 92 )
          break;
        v8 += 2;
        if ( v9 >= String2->Length )
          goto LABEL_115;
      }
      if ( (unsigned __int64)v9 + 6 < String2->Length )
      {
        v10 = (unsigned __int64)v9 >> 1;
        if ( v7[v10] == 59 )
        {
          v11 = v7[v10 + 1];
          if ( ((unsigned __int16)(v11 - 97) <= 0x19u || (unsigned __int16)(v11 - 65) <= 0x19u) && v7[v10 + 2] == 58 )
          {
            v12 = v9 + 6;
            if ( v12 >= String2->Length )
              return 3221225659LL;
            v13 = v7[(unsigned __int64)v12 >> 1];
            if ( (unsigned __int16)(v13 - 48) > 9u
              && (unsigned __int16)(v13 - 97) > 5u
              && (unsigned __int16)(v13 - 65) > 5u )
            {
              return 3221225659LL;
            }
            do
            {
              v12 += 2;
              if ( v12 >= String2->Length )
                break;
              v14 = v7[(unsigned __int64)v12 >> 1];
            }
            while ( (unsigned __int16)(v14 - 48) <= 9u
                 || (unsigned __int16)(v14 - 97) <= 5u
                 || (unsigned __int16)(v14 - 65) <= 5u );
            if ( v12 >= String2->Length )
              return 3221225659LL;
            if ( v7[(unsigned __int64)v12 >> 1] != 92 )
              return 3221225659LL;
            v15 = v12 + 2;
            if ( v15 >= String2->Length )
              return 3221225659LL;
            while ( 1 )
            {
              i = v15 + 2;
              if ( v7[(unsigned __int64)v15 >> 1] == 92 )
                break;
              v15 += 2;
              if ( i >= String2->Length )
                return 3221225659LL;
            }
            while ( i < String2->Length && v7[(unsigned __int64)i >> 1] != 92 )
              i += 2;
          }
        }
      }
    }
  }
LABEL_115:
  v33 = (unsigned __int64)i >> 1;
  if ( i < String2->Length && String2->Buffer[v33] != 92 )
    return 3221225659LL;
  *(_QWORD *)(a2 + 8) = String2->Buffer;
  *(_WORD *)(a2 + 2) = i;
  *(_WORD *)a2 = i;
  if ( i >= String2->Length )
  {
    *(_OWORD *)a3 = 0;
  }
  else
  {
    *(_QWORD *)(a3 + 8) = &String2->Buffer[v33];
    v34 = String2->Length - *(_WORD *)a2;
    *(_WORD *)(a3 + 2) = v34;
    *(_WORD *)a3 = v34;
  }
  return 0;
}

```

## disassembly

```asm
0x18004e358  mov     [rsp-8+arg_18], rbx
0x18004e35d  push    rbp
0x18004e35e  push    rsi
0x18004e35f  push    rdi
0x18004e360  push    r12
0x18004e362  push    r14
0x18004e364  lea     rbp, [rsp-37h]
0x18004e369  sub     rsp, 0E0h
0x18004e370  mov     rax, cs:__security_cookie
0x18004e377  xor     rax, rsp
0x18004e37a  mov     [rbp+57h+var_30], rax
0x18004e37e  lea     rax, aDevice_0; "\\Device\\"
0x18004e385  mov     qword ptr [rbp+57h+var_50.Length], 120010h
0x18004e38d  mov     [rbp+57h+var_50.Buffer], rax
0x18004e391  mov     r14, rdx
0x18004e394  lea     rax, aDeviceMup; "\\Device\\Mup"
0x18004e39b  mov     qword ptr [rbp+57h+String1.Length], 180016h
0x18004e3a3  mov     [rbp+57h+String1.Buffer], rax
0x18004e3a7  mov     rsi, r8
0x18004e3aa  lea     rax, aDeviceHarddisk_0; "\\Device\\HarddiskVolumeShadowCopy"
0x18004e3b1  mov     qword ptr [rbp+57h+var_C0.Length], 420040h
0x18004e3b9  mov     [rbp+57h+var_C0.Buffer], rax
0x18004e3bd  mov     rdi, rcx
0x18004e3c0  lea     rax, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x18004e3c7  mov     qword ptr [rbp+57h+var_B0.Length], 2E002Ch
0x18004e3cf  mov     [rbp+57h+var_B0.Buffer], rax
0x18004e3d3  mov     rdx, rcx; String2
0x18004e3d6  lea     rax, aDeviceCdrom; "\\Device\\CdRom"
0x18004e3dd  mov     qword ptr [rbp+57h+var_A0.Length], 1C001Ah
0x18004e3e5  mov     [rbp+57h+var_A0.Buffer], rax
0x18004e3e9  lea     rcx, [rbp+57h+String1]; String1
0x18004e3ed  lea     rax, aDeviceHarddisk; "\\Device\\Harddisk"
0x18004e3f4  mov     qword ptr [rbp+57h+var_90.Length], 220020h
0x18004e3fc  mov     [rbp+57h+var_90.Buffer], rax
0x18004e400  mov     r8b, 1; CaseInsensitive
0x18004e403  lea     rax, aDeviceVolume; "\\Device\\Volume"
0x18004e40a  mov     qword ptr [rbp+57h+var_80.Length], 1E001Ch
0x18004e412  mov     [rbp+57h+var_80.Buffer], rax
0x18004e416  mov     r12d, 1Ah
0x18004e41c  lea     rax, aDeviceRamdisk; "\\Device\\Ramdisk"
0x18004e423  mov     qword ptr [rbp+57h+var_70.Length], 20001Eh
0x18004e42b  mov     [rbp+57h+var_70.Buffer], rax
0x18004e42f  lea     rax, aDeviceRdpdr; "\\Device\\RdpDr"
0x18004e436  mov     [rbp+57h+var_60.Buffer], rax
0x18004e43a  mov     qword ptr [rbp+57h+var_60.Length], 1C001Ah
0x18004e442  call    cs:__imp_RtlPrefixUnicodeString
0x18004e448  test    al, al
0x18004e44a  jz      loc_18004E5FF
0x18004e450  movzx   ebx, [rbp+57h+String1.Length]
0x18004e454  cmp     bx, [rdi]
0x18004e457  jnb     loc_18004E5F4
0x18004e45d  mov     r8, [rdi+8]
0x18004e461  mov     eax, ebx
0x18004e463  shr     rax, 1
0x18004e466  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e46c  jnz     loc_18004EAA3
0x18004e472  lea     ecx, [rbx+2]
0x18004e475  cmp     cx, [rdi]
0x18004e478  jnb     loc_18004EA38
0x18004e47e  movzx   eax, cx
0x18004e481  shr     rax, 1
0x18004e484  cmp     word ptr [r8+rax*2], 3Bh ; ';'
0x18004e48a  jz      short loc_18004E4C1
0x18004e48c  cmp     cx, [rdi]
0x18004e48f  jnb     loc_18004EA38
0x18004e495  movzx   eax, cx
0x18004e498  lea     edx, [rcx+2]
0x18004e49b  shr     rax, 1
0x18004e49e  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e4a4  jz      short loc_18004E4D2
0x18004e4a6  movzx   ecx, dx
0x18004e4a9  cmp     dx, [rdi]
0x18004e4ac  jb      short loc_18004E495
0x18004e4ae  jmp     loc_18004EA38
0x18004e4b3  movzx   eax, cx
0x18004e4b6  shr     rax, 1
0x18004e4b9  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e4bf  jz      short loc_18004E4CA
0x18004e4c1  add     cx, 2
0x18004e4c5  cmp     cx, [rdi]
0x18004e4c8  jb      short loc_18004E4B3
0x18004e4ca  movzx   ebx, cx
0x18004e4cd  jmp     loc_18004EA38
0x18004e4d2  movzx   eax, word ptr [rdi]
0x18004e4d5  movzx   r9d, dx
0x18004e4d9  lea     rcx, [r9+6]
0x18004e4dd  cmp     rcx, rax
0x18004e4e0  jnb     loc_18004EA38
0x18004e4e6  shr     r9, 1
0x18004e4e9  cmp     word ptr [r8+r9*2], 3Bh ; ';'
0x18004e4ef  jnz     loc_18004EA38
0x18004e4f5  movzx   ecx, word ptr [r8+r9*2+2]
0x18004e4fb  lea     eax, [rcx-61h]
0x18004e4fe  cmp     ax, 19h
0x18004e502  jbe     short loc_18004E512
0x18004e504  sub     cx, 41h ; 'A'
0x18004e508  cmp     cx, 19h
0x18004e50c  ja      loc_18004EA38
0x18004e512  cmp     word ptr [r8+r9*2+4], 3Ah ; ':'
0x18004e519  jnz     loc_18004EA38
0x18004e51f  add     dx, 6
0x18004e523  cmp     dx, [rdi]
0x18004e526  jnb     loc_18004EAA3
0x18004e52c  movzx   eax, dx
0x18004e52f  mov     r9w, 5
0x18004e534  shr     rax, 1
0x18004e537  movzx   ecx, word ptr [r8+rax*2]
0x18004e53c  lea     eax, [rcx-30h]
0x18004e53f  cmp     ax, 9
0x18004e543  jbe     short loc_18004E585
0x18004e545  lea     eax, [rcx-61h]
0x18004e548  cmp     ax, r9w
0x18004e54c  jbe     short loc_18004E585
0x18004e54e  sub     cx, 41h ; 'A'
0x18004e552  cmp     cx, r9w
0x18004e556  ja      loc_18004EAA3
0x18004e55c  jmp     short loc_18004E585
0x18004e55e  movzx   eax, dx
0x18004e561  shr     rax, 1
0x18004e564  movzx   ecx, word ptr [r8+rax*2]
0x18004e569  lea     eax, [rcx-30h]
0x18004e56c  cmp     ax, 9
0x18004e570  jbe     short loc_18004E585
0x18004e572  lea     eax, [rcx-61h]
0x18004e575  cmp     ax, r9w
0x18004e579  jbe     short loc_18004E585
0x18004e57b  sub     cx, 41h ; 'A'
0x18004e57f  cmp     cx, r9w
0x18004e583  ja      short loc_18004E58E
0x18004e585  add     dx, 2
0x18004e589  cmp     dx, [rdi]
0x18004e58c  jb      short loc_18004E55E
0x18004e58e  cmp     dx, [rdi]
0x18004e591  jnb     loc_18004EAA3
0x18004e597  movzx   eax, dx
0x18004e59a  shr     rax, 1
0x18004e59d  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e5a3  jnz     loc_18004EAA3
0x18004e5a9  add     dx, 2
0x18004e5ad  cmp     dx, [rdi]
0x18004e5b0  jnb     loc_18004EAA3
0x18004e5b6  movzx   eax, dx
0x18004e5b9  lea     ebx, [rdx+2]
0x18004e5bc  shr     rax, 1
0x18004e5bf  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e5c5  jz      short loc_18004E5EA
0x18004e5c7  movzx   edx, bx
0x18004e5ca  cmp     bx, [rdi]
0x18004e5cd  jb      short loc_18004E5B6
0x18004e5cf  jmp     loc_18004EAA3
0x18004e5d4  movzx   eax, bx
0x18004e5d7  shr     rax, 1
0x18004e5da  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x18004e5e0  jz      loc_18004EA38
0x18004e5e6  add     bx, 2
0x18004e5ea  cmp     bx, [rdi]
0x18004e5ed  jb      short loc_18004E5D4
0x18004e5ef  jmp     loc_18004EA38
0x18004e5f4  jnz     loc_18004EAA3
0x18004e5fa  jmp     loc_18004EA38
0x18004e5ff  mov     r8b, 1; CaseInsensitive
0x18004e602  lea     rcx, [rbp+57h+var_C0]; String1
0x18004e606  mov     rdx, rdi; String2
0x18004e609  call    cs:__imp_RtlPrefixUnicodeString
0x18004e60f  test    al, al
0x18004e611  jz      short loc_18004E64A
0x18004e613  movzx   ebx, [rbp+57h+var_C0.Length]
0x18004e617  cmp     bx, [rdi]
0x18004e61a  jnb     loc_18004EA38
0x18004e620  mov     rdx, [rdi+8]
0x18004e624  movzx   eax, bx
0x18004e627  shr     rax, 1
0x18004e62a  movzx   ecx, word ptr [rdx+rax*2]
0x18004e62e  sub     cx, 30h ; '0'
0x18004e632  cmp     cx, 9
0x18004e636  ja      loc_18004EA38
0x18004e63c  add     bx, 2
0x18004e640  cmp     bx, [rdi]
0x18004e643  jb      short loc_18004E624
0x18004e645  jmp     loc_18004EA38
0x18004e64a  mov     r8b, 1; CaseInsensitive
0x18004e64d  lea     rcx, [rbp+57h+var_B0]; String1
0x18004e651  mov     rdx, rdi; String2
0x18004e654  call    cs:__imp_RtlPrefixUnicodeString
0x18004e65a  test    al, al
0x18004e65c  jz      short loc_18004E695
0x18004e65e  movzx   ebx, [rbp+57h+var_B0.Length]
0x18004e662  cmp     bx, [rdi]
0x18004e665  jnb     loc_18004EA38
0x18004e66b  mov     rdx, [rdi+8]
0x18004e66f  movzx   eax, bx
0x18004e672  shr     rax, 1
0x18004e675  movzx   ecx, word ptr [rdx+rax*2]
0x18004e679  sub     cx, 30h ; '0'
0x18004e67d  cmp     cx, 9
0x18004e681  ja      loc_18004EA38
0x18004e687  add     bx, 2
0x18004e68b  cmp     bx, [rdi]
0x18004e68e  jb      short loc_18004E66F
0x18004e690  jmp     loc_18004EA38
0x18004e695  mov     r8b, 1; CaseInsensitive
0x18004e698  lea     rcx, [rbp+57h+var_A0]; String1
0x18004e69c  mov     rdx, rdi; String2
0x18004e69f  call    cs:__imp_RtlPrefixUnicodeString
0x18004e6a5  test    al, al
0x18004e6a7  jz      short loc_18004E6E0
0x18004e6a9  movzx   ebx, [rbp+57h+var_A0.Length]
0x18004e6ad  cmp     bx, [rdi]
0x18004e6b0  jnb     loc_18004EA38
0x18004e6b6  mov     rdx, [rdi+8]
0x18004e6ba  movzx   eax, bx
0x18004e6bd  shr     rax, 1
0x18004e6c0  movzx   ecx, word ptr [rdx+rax*2]
0x18004e6c4  sub     cx, 30h ; '0'
0x18004e6c8  cmp     cx, 9
0x18004e6cc  ja      loc_18004EA38
0x18004e6d2  add     bx, 2
0x18004e6d6  cmp     bx, [rdi]
0x18004e6d9  jb      short loc_18004E6BA
0x18004e6db  jmp     loc_18004EA38
0x18004e6e0  mov     r8b, 1; CaseInsensitive
0x18004e6e3  lea     rcx, [rbp+57h+var_90]; String1
0x18004e6e7  mov     rdx, rdi; String2
0x18004e6ea  call    cs:__imp_RtlPrefixUnicodeString
0x18004e6f0  test    al, al
0x18004e6f2  jz      loc_18004E7AB
0x18004e6f8  movzx   ebx, [rbp+57h+var_90.Length]
0x18004e6fc  cmp     bx, [rdi]
0x18004e6ff  jnb     loc_18004EAA3
0x18004e705  mov     rdx, [rdi+8]
0x18004e709  movzx   eax, bx
0x18004e70c  shr     rax, 1
0x18004e70f  movzx   ecx, word ptr [rdx+rax*2]
0x18004e713  sub     cx, 30h ; '0'
0x18004e717  cmp     cx, 9
0x18004e71b  ja      short loc_18004E72B
0x18004e71d  add     bx, 2
0x18004e721  cmp     bx, [rdi]
0x18004e724  jb      short loc_18004E709
0x18004e726  jmp     loc_18004EAA3
0x18004e72b  movzx   eax, bx
0x18004e72e  shr     rax, 1
0x18004e731  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x18004e736  jnz     loc_18004EAA3
0x18004e73c  jmp     short loc_18004E75B
0x18004e73e  movzx   eax, bx
0x18004e741  shr     rax, 1
0x18004e744  movzx   ecx, word ptr [rdx+rax*2]
0x18004e748  lea     eax, [rcx-61h]
0x18004e74b  cmp     ax, 19h
0x18004e74f  jbe     short loc_18004E75B
0x18004e751  sub     cx, 41h ; 'A'
0x18004e755  cmp     cx, 19h
0x18004e759  ja      short loc_18004E764
0x18004e75b  add     bx, 2
0x18004e75f  cmp     bx, [rdi]
0x18004e762  jb      short loc_18004E73E
0x18004e764  cmp     bx, [rdi]
0x18004e767  jnb     loc_18004EAA3
0x18004e76d  movzx   eax, bx
0x18004e770  shr     rax, 1
0x18004e773  movzx   ecx, word ptr [rdx+rax*2]
0x18004e777  sub     cx, 30h ; '0'
0x18004e77b  cmp     cx, 9
0x18004e77f  ja      loc_18004EAA3
0x18004e785  movzx   eax, bx
0x18004e788  shr     rax, 1
0x18004e78b  movzx   ecx, word ptr [rdx+rax*2]
0x18004e78f  sub     cx, 30h ; '0'
0x18004e793  cmp     cx, 9
0x18004e797  ja      loc_18004EA38
0x18004e79d  add     bx, 2
0x18004e7a1  cmp     bx, [rdi]
0x18004e7a4  jb      short loc_18004E785
0x18004e7a6  jmp     loc_18004EA38
0x18004e7ab  mov     r8b, 1; CaseInsensitive
0x18004e7ae  lea     rcx, [rbp+57h+var_80]; String1
0x18004e7b2  mov     rdx, rdi; String2
0x18004e7b5  call    cs:__imp_RtlPrefixUnicodeString
0x18004e7bb  test    al, al
0x18004e7bd  jz      short loc_18004E831
0x18004e7bf  movzx   edx, [rbp+57h+var_80.Length]
0x18004e7c3  movzx   ebx, dx
0x18004e7c6  cmp     dx, [rdi]
0x18004e7c9  jnb     short loc_18004E80B
0x18004e7cb  mov     r8, [rdi+8]
0x18004e7cf  mov     r9, 3FFFFFF01FF9h
0x18004e7d9  movzx   eax, bx
0x18004e7dc  shr     rax, 1
0x18004e7df  movzx   ecx, word ptr [r8+rax*2]
0x18004e7e4  lea     eax, [rcx-61h]
0x18004e7e7  cmp     ax, r12w
0x18004e7eb  jbe     short loc_18004E802
0x18004e7ed  lea     eax, [rcx-2Dh]
0x18004e7f0  cmp     ax, 2Dh ; '-'
0x18004e7f4  ja      short loc_18004E7FC
0x18004e7f6  bt      r9, rax
0x18004e7fa  jb      short loc_18004E802
0x18004e7fc  cmp     cx, 7Dh ; '}'
0x18004e800  jnz     short loc_18004E80B
  ... truncated ...
```

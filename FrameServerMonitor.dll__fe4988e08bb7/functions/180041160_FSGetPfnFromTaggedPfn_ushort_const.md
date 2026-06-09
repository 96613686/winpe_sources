# FSGetPfnFromTaggedPfn(ushort const *)

- ea: `0x180041160`
- end: `0x18004123e`
- name: `?FSGetPfnFromTaggedPfn@@YAPEBGPEBG@Z`
- size: `222`
- prototype: `LPCWCH __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800141c4`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18000cadc`
- `0x180041160`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004120e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004120e`

## pseudocode

```c
LPCWCH __fastcall FSGetPfnFromTaggedPfn(LPCWCH lpString1)
{
  __int64 v1; // rdi
  int v3; // ecx
  __int64 v4; // rdx
  int v5; // r8d
  unsigned __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  v7 = 0;
  if ( lpString1 )
  {
    if ( (int)StringCchLengthW(lpString1, 0x7FFFFFFFu, &v7) >= 0 )
    {
      if ( v7 > 4 )
      {
        if ( CompareStringOrdinal(lpString1, 4, L"pfn:", 4, 1) == 2 )
        {
          return lpString1 + 4;
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v4 = 71;
          goto LABEL_4;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 70;
        goto LABEL_4;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v5);
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v4 = (unsigned int)(v3 + 68);
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, -2147024809);
  }
  return (LPCWCH)v1;
}

```

## disassembly

```asm
0x180041160  mov     [rsp+arg_8], rbx
0x180041165  push    rdi
0x180041166  sub     rsp, 30h
0x18004116a  xor     edi, edi
0x18004116c  mov     rbx, rcx
0x18004116f  mov     [rsp+38h+arg_0], rdi
0x180041174  test    rcx, rcx
0x180041177  jnz     short loc_1800411B0
0x180041179  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004117e  cmp     al, 1
0x180041180  jb      loc_180041230
0x180041186  lea     edx, [rcx+44h]
0x180041189  mov     [rsp+38h+bIgnoreCase], 80070057h
0x180041191  mov     rcx, cs:WPP_GLOBAL_Control
0x180041198  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18004119f  xor     r9d, r9d
0x1800411a2  mov     rcx, [rcx+10h]
0x1800411a6  call    WPP_SF_qD
0x1800411ab  jmp     loc_180041230
0x1800411b0  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x1800411b5  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800411ba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800411bf  mov     r8d, eax
0x1800411c2  test    eax, eax
0x1800411c4  jns     short loc_1800411DB
0x1800411c6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800411cb  cmp     al, 1
0x1800411cd  jb      short loc_180041230
0x1800411cf  mov     edx, 45h ; 'E'
0x1800411d4  mov     [rsp+38h+bIgnoreCase], r8d
0x1800411d9  jmp     short loc_180041191
0x1800411db  cmp     [rsp+38h+arg_0], 4
0x1800411e1  ja      short loc_1800411F3
0x1800411e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800411e8  cmp     al, 1
0x1800411ea  jb      short loc_180041230
0x1800411ec  mov     edx, 46h ; 'F'
0x1800411f1  jmp     short loc_180041189
0x1800411f3  mov     r9d, 4; cchCount2
0x1800411f9  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180041201  mov     edx, r9d; cchCount1
0x180041204  lea     r8, aPfn; "pfn:"
0x18004120b  mov     rcx, rbx; lpString1
0x18004120e  call    cs:__imp_CompareStringOrdinal
0x180041214  cmp     eax, 2
0x180041217  jz      short loc_18004122C
0x180041219  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004121e  cmp     al, 1
0x180041220  jb      short loc_180041230
0x180041222  mov     edx, 47h ; 'G'
0x180041227  jmp     loc_180041189
0x18004122c  lea     rdi, [rbx+8]
0x180041230  mov     rbx, [rsp+38h+arg_8]
0x180041235  mov     rax, rdi
0x180041238  add     rsp, 30h
0x18004123c  pop     rdi
0x18004123d  retn
```

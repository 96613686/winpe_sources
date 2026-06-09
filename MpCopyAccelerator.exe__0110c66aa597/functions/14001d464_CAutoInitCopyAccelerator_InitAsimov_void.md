# CAutoInitCopyAccelerator::InitAsimov(void)

- ea: `0x14001d464`
- end: `0x14001d6fd`
- name: `?InitAsimov@CAutoInitCopyAccelerator@@AEAAJXZ`
- size: `665`
- prototype: `__int64 __fastcall(CAutoInitCopyAccelerator *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140002b9c`
- `0x140002e74`
- `0x14000309c`
- `0x140003254`
- `0x140003414`
- `0x140005c20`
- `0x140005c40`
- `0x14001d2b4`
- `0x14001d464`
- `0x14001da70`
- `0x14001dac4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAutoInitCopyAccelerator::InitAsimov(CAutoInitCopyAccelerator *this, __int64 a2, const wchar_t *a3)
{
  int ModuleVersion; // eax
  int v4; // edx
  int v5; // eax
  int v6; // edx
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rcx
  int *v13; // rdx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 result; // rax
  __int64 v21; // r9
  _QWORD *v22; // rcx
  __int64 v23; // [rsp+0h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+20h] [rbp-98h]
  __int64 v25; // [rsp+28h] [rbp-90h]
  void *v26; // [rsp+30h] [rbp-88h] BYREF
  void *v27; // [rsp+38h] [rbp-80h] BYREF
  const std::exception *v28; // [rsp+40h] [rbp-78h] BYREF
  void *v29; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v31[8]; // [rsp+60h] [rbp-58h] BYREF

  v29 = 0;
  v30 = 0;
  ModuleVersion = CommonUtil::UtilGetModuleVersion((CommonUtil *)&v30, 0, a3);
  if ( ModuleVersion < 0 )
  {
    try
    {
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)ModuleVersion, v4);
    }
    catch ( const std::exception *v28 )
    {
      CommonUtil::HrFromStdException(v28, (const struct std::exception *)&v23);
    }
    catch ( ... )
    {
      LODWORD(v26) = -2147467259;
      v21 = (unsigned int)v26;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
        WPP_SF_d(v22[2], 14, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids, v21);
LABEL_3:
      v31[0] = 0;
      v7 = (__int64 *)CommonUtil::TrDuplicateStringW(&v26, &dword_140033A5C);
      v8 = *v7;
      *v7 = 0;
      v31[1] = v8;
      if ( v26 )
        operator delete(v26);
      v9 = (__int64 *)CommonUtil::TrDuplicateStringW(&v27, &dword_140033A5C);
      v10 = *v9;
      *v9 = 0;
      v31[2] = v10;
      if ( v27 )
        operator delete(v27);
      v11 = (__int64 *)CommonUtil::TrDuplicateStringW(&v26, &dword_140033A5C);
      v12 = *v11;
      *v11 = 0;
      v31[3] = v12;
      if ( v26 )
        operator delete(v26);
      v13 = &dword_140033A5C;
      if ( v29 )
        v13 = (int *)v29;
      v14 = (__int64 *)CommonUtil::TrDuplicateStringW(&v27, v13);
      v15 = *v14;
      *v14 = 0;
      v31[4] = v15;
      if ( v27 )
        operator delete(v27);
      v16 = (__int64 *)CommonUtil::TrDuplicateStringW(&v26, &dword_140033A5C);
      v17 = *v16;
      *v16 = 0;
      v31[5] = v17;
      if ( v26 )
        operator delete(v26);
      v18 = (__int64 *)CommonUtil::TrDuplicateStringW(&v27, &dword_140033A5C);
      v19 = *v18;
      *v18 = 0;
      v31[6] = v19;
      if ( v27 )
        operator delete(v27);
      v31[7] = 0;
      InitializeMpAsimov(v31);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids, v29);
      AsimovDefaultData::~AsimovDefaultData((AsimovDefaultData *)v31);
      if ( v29 )
        operator delete(v29);
      result = 0;
    }
  }
  LODWORD(v25) = (unsigned __int16)v30;
  LODWORD(v24) = WORD1(v30);
  v5 = CommonUtil::NewSprintfW(
         (CommonUtil *)&v29,
         (wchar_t **)L"%d.%d.%d.%d",
         (const wchar_t *)HIWORD(v30),
         WORD2(v30),
         v24,
         v25);
  if ( v5 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v5, v6);
  goto LABEL_3;
}

```

## disassembly

```asm
0x14001d464  mov     r11, rsp
0x14001d467  mov     [r11+8], rsi
0x14001d46b  push    r14
0x14001d46d  sub     rsp, 0B0h
0x14001d474  mov     rax, cs:__security_cookie
0x14001d47b  xor     rax, rsp
0x14001d47e  mov     [rsp+0B8h+var_18], rax
0x14001d486  mov     qword ptr [r11-70h], 0
0x14001d48e  mov     qword ptr [r11-68h], 0
0x14001d496  xor     edx, edx; unsigned __int64 *
0x14001d498  lea     rcx, [r11-68h]; this
0x14001d49c  call    ?UtilGetModuleVersion@CommonUtil@@YAJPEA_KPEB_W@Z; CommonUtil::UtilGetModuleVersion(unsigned __int64 *,wchar_t const *)
0x14001d4a1  test    eax, eax
0x14001d4a3  js      loc_14001D6ED
0x14001d4a9  mov     r8, [rsp+0B8h+var_68]
0x14001d4ae  movzx   edx, r8w
0x14001d4b2  mov     rax, r8
0x14001d4b5  shr     rax, 10h
0x14001d4b9  movzx   ecx, ax
0x14001d4bc  mov     rax, r8
0x14001d4bf  shr     rax, 20h
0x14001d4c3  movzx   r9d, ax
0x14001d4c7  shr     r8, 30h; wchar_t *
0x14001d4cb  mov     dword ptr [rsp+0B8h+var_90], edx
0x14001d4cf  mov     dword ptr [rsp+0B8h+var_98], ecx
0x14001d4d3  lea     rdx, aDDDD; "%d.%d.%d.%d"
0x14001d4da  lea     rcx, [rsp+0B8h+var_70]; this
0x14001d4df  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x14001d4e4  test    eax, eax
0x14001d4e6  js      loc_14001D6F4
0x14001d4ec  lea     rsi, WPP_GLOBAL_Control
0x14001d4f3  mov     [rsp+0B8h+var_58], 0
0x14001d4fc  lea     r14, dword_140033A5C
0x14001d503  mov     rdx, r14
0x14001d506  lea     rcx, [rsp+0B8h+var_88]
0x14001d50b  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d510  mov     rcx, [rax]
0x14001d513  mov     qword ptr [rax], 0
0x14001d51a  mov     [rsp+0B8h+var_50], rcx
0x14001d51f  mov     rcx, [rsp+0B8h+var_88]; void *
0x14001d524  test    rcx, rcx
0x14001d527  jz      short loc_14001D52E
0x14001d529  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d52e  mov     rdx, r14
0x14001d531  lea     rcx, [rsp+0B8h+var_80]
0x14001d536  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d53b  mov     rcx, [rax]
0x14001d53e  mov     qword ptr [rax], 0
0x14001d545  mov     [rsp+0B8h+var_48], rcx
0x14001d54a  mov     rcx, [rsp+0B8h+var_80]; void *
0x14001d54f  test    rcx, rcx
0x14001d552  jz      short loc_14001D559
0x14001d554  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d559  mov     rdx, r14
0x14001d55c  lea     rcx, [rsp+0B8h+var_88]
0x14001d561  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d566  mov     rcx, [rax]
0x14001d569  mov     qword ptr [rax], 0
0x14001d570  mov     [rsp+0B8h+var_40], rcx
0x14001d575  mov     rcx, [rsp+0B8h+var_88]; void *
0x14001d57a  test    rcx, rcx
0x14001d57d  jz      short loc_14001D584
0x14001d57f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d584  mov     rdx, r14
0x14001d587  cmp     [rsp+0B8h+var_70], 0
0x14001d58d  cmovnz  rdx, [rsp+0B8h+var_70]
0x14001d593  lea     rcx, [rsp+0B8h+var_80]
0x14001d598  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d59d  mov     rcx, [rax]
0x14001d5a0  mov     qword ptr [rax], 0
0x14001d5a7  mov     [rsp+0B8h+var_38], rcx
0x14001d5af  mov     rcx, [rsp+0B8h+var_80]; void *
0x14001d5b4  test    rcx, rcx
0x14001d5b7  jz      short loc_14001D5BE
0x14001d5b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d5be  mov     rdx, r14
0x14001d5c1  lea     rcx, [rsp+0B8h+var_88]
0x14001d5c6  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d5cb  mov     rcx, [rax]
0x14001d5ce  mov     qword ptr [rax], 0
0x14001d5d5  mov     [rsp+0B8h+var_30], rcx
0x14001d5dd  mov     rcx, [rsp+0B8h+var_88]; void *
0x14001d5e2  test    rcx, rcx
0x14001d5e5  jz      short loc_14001D5EC
0x14001d5e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d5ec  mov     rdx, r14
0x14001d5ef  lea     rcx, [rsp+0B8h+var_80]
0x14001d5f4  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x14001d5f9  mov     rcx, [rax]
0x14001d5fc  mov     qword ptr [rax], 0
0x14001d603  mov     [rsp+0B8h+var_28], rcx
0x14001d60b  mov     rcx, [rsp+0B8h+var_80]; void *
0x14001d610  test    rcx, rcx
0x14001d613  jz      short loc_14001D61A
0x14001d615  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d61a  mov     [rsp+0B8h+var_20], 0
0x14001d626  lea     rcx, [rsp+0B8h+var_58]
0x14001d62b  call    ?InitializeMpAsimov@@YAX$$QEAUAsimovDefaultData@@@Z; InitializeMpAsimov(AsimovDefaultData &&)
0x14001d630  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d637  cmp     rcx, rsi
0x14001d63a  jz      short loc_14001D65C
0x14001d63c  test    byte ptr [rcx+1Ch], 4
0x14001d640  jz      short loc_14001D65C
0x14001d642  mov     edx, 0Fh
0x14001d647  mov     r9, [rsp+0B8h+var_70]
0x14001d64c  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001d653  mov     rcx, [rcx+10h]
0x14001d657  call    WPP_SF_S
0x14001d65c  lea     rcx, [rsp+0B8h+var_58]; this
0x14001d661  call    ??1AsimovDefaultData@@QEAA@XZ; AsimovDefaultData::~AsimovDefaultData(void)
0x14001d666  nop
0x14001d667  cmp     [rsp+0B8h+var_70], 0
0x14001d66d  jz      short loc_14001D679
0x14001d66f  mov     rcx, [rsp+0B8h+var_70]; void *
0x14001d674  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d679  xor     eax, eax
0x14001d67b  mov     rcx, [rsp+0B8h+var_18]
0x14001d683  xor     rcx, rsp; StackCookie
0x14001d686  call    __security_check_cookie
0x14001d68b  mov     rsi, [rsp+0B8h+arg_0]
0x14001d693  add     rsp, 0B0h
0x14001d69a  pop     r14
0x14001d69c  retn
0x14001d69d  mov     r9d, dword ptr [rsp+0B8h+var_88]
0x14001d6a2  jmp     short loc_14001D6B2
0x14001d6a4  mov     r9d, dword ptr [rsp+0B8h+var_88]
0x14001d6a9  test    r9d, r9d
0x14001d6ac  jns     loc_14001D4EC
0x14001d6b2  lea     rsi, WPP_GLOBAL_Control
0x14001d6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6c0  cmp     rcx, rsi
0x14001d6c3  jz      loc_14001D4F3
0x14001d6c9  test    byte ptr [rcx+1Ch], 2
0x14001d6cd  jz      loc_14001D4F3
0x14001d6d3  mov     edx, 0Eh
0x14001d6d8  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001d6df  mov     rcx, [rcx+10h]
0x14001d6e3  call    WPP_SF_d
0x14001d6e8  jmp     loc_14001D4F3
0x14001d6ed  mov     ecx, eax; this
0x14001d6ef  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x14001d6f4  mov     ecx, eax; this
0x14001d6f6  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```

# CUserStateManager::ClearCachedCredentials(void)

- ea: `0x1800371c0`
- end: `0x180037468`
- name: `?ClearCachedCredentials@CUserStateManager@@QEAAXXZ`
- size: `680`
- prototype: `void __fastcall(CUserStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024884`
- `0x18003797c`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180011314`
- `0x18001133c`
- `0x1800371c0`
- `0x18003b420`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037358`
- `KERNEL32!GetLastError` at `0x180037358`
- `ADVAPI32!CredDeleteW` at `0x18003734e`
- `ADVAPI32!CredDeleteW` at `0x18003734e`

## string_xrefs

- `0x180037230`: `CUserStateManager::ClearCachedCredentials`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUserStateManager::ClearCachedCredentials(CUserStateManager *this)
{
  _BYTE *v1; // rax
  char v2; // al
  int v3; // eax
  int v4; // eax
  DWORD LastError; // eax
  signed int v6; // edi
  int v7; // [rsp+30h] [rbp-68h] BYREF
  int v8; // [rsp+34h] [rbp-64h]
  char v9; // [rsp+38h] [rbp-60h]
  const char *v10; // [rsp+40h] [rbp-58h]
  __int64 v11; // [rsp+48h] [rbp-50h]
  int pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  int v13; // [rsp+54h] [rbp-44h] BYREF
  int v14; // [rsp+58h] [rbp-40h] BYREF
  int v15; // [rsp+5Ch] [rbp-3Ch] BYREF
  int v16; // [rsp+60h] [rbp-38h] BYREF
  const ATL::CAtlException *v17; // [rsp+68h] [rbp-30h] BYREF
  const ATL::CAtlException *v18; // [rsp+70h] [rbp-28h] BYREF
  int v20; // [rsp+A8h] [rbp+10h]
  int v21; // [rsp+B0h] [rbp+18h]
  int v22; // [rsp+B8h] [rbp+20h]

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v2 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
  }
  if ( (v1[68] & 8) == 0 || v1[65] < 6u )
    goto LABEL_8;
  v2 = 1;
LABEL_9:
  v7 = 0;
  v8 = 1096;
  v9 = v2;
  v10 = "CUserStateManager::ClearCachedCredentials";
  v11 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  try
  {
    (*(void (__fastcall **)(CUserStateManager *))(*(_QWORD *)this + 16LL))(this);
  }
  catch ( long v15 )
  {
    v7 = v15;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v8) = 1106;
    v7 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v8) = 1106;
    v7 = -2147418113;
  }
  catch ( const ATL::CAtlException *v17 )
  {
    HIWORD(v8) = 1106;
    v7 = *(_DWORD *)v17;
  }
  v3 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        67,
        WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids,
        (unsigned int)v7);
      v3 = v7;
    }
    v20 = v3;
    v7 = 0;
  }
  try
  {
    CUserStateManager::SetAdfsCredentialInternal(this, &Format, 0, &Format, 0, 1);
  }
  catch ( long v16 )
  {
    v7 = v16;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v8) = 1118;
    v7 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v8) = 1118;
    v7 = -2147418113;
  }
  catch ( const ATL::CAtlException *v18 )
  {
    HIWORD(v8) = 1118;
    v7 = *(_DWORD *)v18;
  }
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        68,
        WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids,
        (unsigned int)v7);
      v4 = v7;
    }
    v21 = v4;
    v7 = 0;
  }
  if ( !CredDeleteW(L"Microsoft.WorkFolders.Generic", 1u, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 1168 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids, LastError);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v22 = v6;
    }
  }
  v7 = v20;
  if ( v20 < 0 )
  {
    HIWORD(v8) = 1136;
    pExceptionObject = v20;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v8) = 1136;
  v7 = v21;
  if ( v21 < 0 )
  {
    HIWORD(v8) = 1137;
    v13 = v21;
    throw (long *)&v13;
  }
  LOWORD(v8) = 1137;
  v7 = v22;
  if ( v22 < 0 )
  {
    HIWORD(v8) = 1138;
    v14 = v22;
    throw (long *)&v14;
  }
  LOWORD(v8) = 1138;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v7);
}

```

## disassembly

```asm
0x1800371c0  mov     [rsp+arg_0], rcx
0x1800371c5  push    rbx
0x1800371c6  push    rsi
0x1800371c7  push    rdi
0x1800371c8  sub     rsp, 80h
0x1800371cf  lea     rsi, WPP_GLOBAL_Control
0x1800371d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800371dd  cmp     rax, rsi
0x1800371e0  jz      short loc_18003720A
0x1800371e2  test    byte ptr [rax+44h], 8
0x1800371e6  jz      short loc_18003721C
0x1800371e8  cmp     byte ptr [rax+41h], 6
0x1800371ec  jb      short loc_18003720A
0x1800371ee  mov     edx, 42h ; 'B'
0x1800371f3  lea     r8, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids
0x1800371fa  mov     rcx, [rax+38h]
0x1800371fe  call    WPP_SF_
0x180037203  mov     rax, cs:WPP_GLOBAL_Control
0x18003720a  test    byte ptr [rax+44h], 8
0x18003720e  jz      short loc_18003721C
0x180037210  cmp     byte ptr [rax+41h], 6
0x180037214  jb      short loc_18003721C
0x180037216  mov     al, 1
0x180037218  xor     ebx, ebx
0x18003721a  jmp     short loc_180037220
0x18003721c  xor     ebx, ebx
0x18003721e  mov     al, bl
0x180037220  mov     [rsp+98h+var_68], ebx
0x180037224  mov     [rsp+98h+var_64], 448h
0x18003722c  mov     [rsp+98h+var_60], al
0x180037230  lea     rax, aCuserstatemana_4; "CUserStateManager::ClearCachedCredentia"...
0x180037237  mov     [rsp+98h+var_58], rax
0x18003723c  mov     [rsp+98h+var_50], rbx
0x180037241  mov     [rsp+98h+arg_8], ebx
0x180037248  mov     [rsp+98h+arg_10], ebx
0x18003724f  mov     [rsp+98h+arg_18], ebx
0x180037256  mov     rcx, [rsp+98h+arg_0]
0x18003725e  mov     rax, [rcx]
0x180037261  mov     rax, [rax+10h]
0x180037265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003726a  nop
0x18003726b  jmp     short loc_18003727C
0x18003726d  jmp     short loc_180037273
0x18003726f  jmp     short loc_180037273
0x180037271  jmp     short $+2
0x180037273  xor     ebx, ebx
0x180037275  lea     rsi, WPP_GLOBAL_Control
0x18003727c  mov     eax, [rsp+98h+var_68]
0x180037280  test    eax, eax
0x180037282  jns     short loc_1800372C3
0x180037284  mov     rcx, cs:WPP_GLOBAL_Control
0x18003728b  cmp     rcx, rsi
0x18003728e  jz      short loc_1800372B8
0x180037290  test    byte ptr [rcx+44h], 8
0x180037294  jz      short loc_1800372B8
0x180037296  cmp     byte ptr [rcx+41h], 3
0x18003729a  jb      short loc_1800372B8
0x18003729c  mov     edx, 43h ; 'C'
0x1800372a1  mov     r9d, eax
0x1800372a4  lea     r8, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids
0x1800372ab  mov     rcx, [rcx+38h]
0x1800372af  call    WPP_SF_d
0x1800372b4  mov     eax, [rsp+98h+var_68]
0x1800372b8  mov     [rsp+98h+arg_8], eax
0x1800372bf  mov     [rsp+98h+var_68], ebx
0x1800372c3  mov     [rsp+98h+var_70], 1; bool
0x1800372c8  mov     [rsp+98h+var_78], rbx; unsigned __int16 *
0x1800372cd  lea     rdx, Format; unsigned __int16 *
0x1800372d4  mov     r9, rdx; unsigned __int16 *
0x1800372d7  xor     r8d, r8d; unsigned __int16 *
0x1800372da  mov     rcx, [rsp+98h+arg_0]; this
0x1800372e2  call    ?SetAdfsCredentialInternal@CUserStateManager@@AEAAXPEBG000_N@Z; CUserStateManager::SetAdfsCredentialInternal(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x1800372e7  nop
0x1800372e8  jmp     short loc_1800372F9
0x1800372ea  jmp     short loc_1800372F0
0x1800372ec  jmp     short loc_1800372F0
0x1800372ee  jmp     short $+2
0x1800372f0  xor     ebx, ebx
0x1800372f2  lea     rsi, WPP_GLOBAL_Control
0x1800372f9  mov     eax, [rsp+98h+var_68]
0x1800372fd  test    eax, eax
0x1800372ff  jns     short loc_180037340
0x180037301  mov     rcx, cs:WPP_GLOBAL_Control
0x180037308  cmp     rcx, rsi
0x18003730b  jz      short loc_180037335
0x18003730d  test    byte ptr [rcx+44h], 8
0x180037311  jz      short loc_180037335
0x180037313  cmp     byte ptr [rcx+41h], 3
0x180037317  jb      short loc_180037335
0x180037319  mov     edx, 44h ; 'D'
0x18003731e  mov     r9d, eax
0x180037321  lea     r8, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids
0x180037328  mov     rcx, [rcx+38h]
0x18003732c  call    WPP_SF_d
0x180037331  mov     eax, [rsp+98h+var_68]
0x180037335  mov     [rsp+98h+arg_10], eax
0x18003733c  mov     [rsp+98h+var_68], ebx
0x180037340  xor     r8d, r8d; Flags
0x180037343  lea     edx, [r8+1]; Type
0x180037347  lea     rcx, TargetName; "Microsoft.WorkFolders.Generic"
0x18003734e  call    cs:__imp_CredDeleteW
0x180037354  test    eax, eax
0x180037356  jnz     short loc_1800373AB
0x180037358  call    cs:__imp_GetLastError
0x18003735e  mov     edi, eax
0x180037360  cmp     eax, 490h
0x180037365  jz      short loc_1800373AB
0x180037367  mov     rcx, cs:WPP_GLOBAL_Control
0x18003736e  cmp     rcx, rsi
0x180037371  jz      short loc_180037397
0x180037373  test    byte ptr [rcx+44h], 8
0x180037377  jz      short loc_180037397
0x180037379  cmp     byte ptr [rcx+41h], 3
0x18003737d  jb      short loc_180037397
0x18003737f  mov     edx, 45h ; 'E'
0x180037384  mov     r9d, eax
0x180037387  lea     r8, WPP_b6e0a22bd8dc39d7e38d31cd7cb220fe_Traceguids
0x18003738e  mov     rcx, [rcx+38h]
0x180037392  call    WPP_SF_d
0x180037397  test    edi, edi
0x180037399  jle     short loc_1800373A4
0x18003739b  movzx   edi, di
0x18003739e  or      edi, 80070000h
0x1800373a4  mov     [rsp+98h+arg_18], edi
0x1800373ab  mov     eax, [rsp+98h+arg_8]
0x1800373b2  mov     [rsp+98h+var_68], eax
0x1800373b6  mov     [rsp+98h+var_68], eax
0x1800373ba  mov     ecx, 470h
0x1800373bf  test    eax, eax
0x1800373c1  jns     short loc_1800373DE
0x1800373c3  mov     word ptr [rsp+98h+var_64+2], cx
0x1800373c8  mov     [rsp+98h+pExceptionObject], eax
0x1800373cc  lea     rdx, _TI1J; pThrowInfo
0x1800373d3  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800373d8  call    _CxxThrowException_0
0x1800373de  mov     word ptr [rsp+98h+var_64], cx
0x1800373e3  mov     eax, [rsp+98h+arg_10]
0x1800373ea  mov     [rsp+98h+var_68], eax
0x1800373ee  mov     [rsp+98h+var_68], eax
0x1800373f2  mov     ecx, 471h
0x1800373f7  test    eax, eax
0x1800373f9  jns     short loc_180037416
0x1800373fb  mov     word ptr [rsp+98h+var_64+2], cx
0x180037400  mov     [rsp+98h+var_44], eax
0x180037404  lea     rdx, _TI1J; pThrowInfo
0x18003740b  lea     rcx, [rsp+98h+var_44]; pExceptionObject
0x180037410  call    _CxxThrowException_0
0x180037416  mov     word ptr [rsp+98h+var_64], cx
0x18003741b  mov     eax, [rsp+98h+arg_18]
0x180037422  mov     [rsp+98h+var_68], eax
0x180037426  mov     [rsp+98h+var_68], eax
0x18003742a  mov     ecx, 472h
0x18003742f  test    eax, eax
0x180037431  jns     short loc_18003744E
0x180037433  mov     word ptr [rsp+98h+var_64+2], cx
0x180037438  mov     [rsp+98h+var_40], eax
0x18003743c  lea     rdx, _TI1J; pThrowInfo
0x180037443  lea     rcx, [rsp+98h+var_40]; pExceptionObject
0x180037448  call    _CxxThrowException_0
0x18003744e  mov     word ptr [rsp+98h+var_64], cx
0x180037453  lea     rcx, [rsp+98h+var_68]; this
0x180037458  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003745d  add     rsp, 80h
0x180037464  pop     rdi
0x180037465  pop     rsi
0x180037466  pop     rbx
0x180037467  retn
```

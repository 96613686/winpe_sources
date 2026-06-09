# CPnpNotification::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x18000c5a0`
- end: `0x18000cb3b`
- name: `?OnUpdate@CPnpNotification@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(CPnpNotification *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x18000bc18`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000c5a0`
- `0x18000cbf8`
- `0x18000d2a8`
- `0x18000d338`
- `0x18000d404`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c77a`
- `msvcrt!_wcsicmp` at `0x18000c8ed`
- `msvcrt!_wcsicmp` at `0x18000c77a`
- `msvcrt!_wcsicmp` at `0x18000c8ed`
- `KERNEL32!LeaveCriticalSection` at `0x18000ca66`
- `KERNEL32!LeaveCriticalSection` at `0x18000ca66`
- `KERNEL32!EnterCriticalSection` at `0x18000c85d`
- `KERNEL32!EnterCriticalSection` at `0x18000c85d`
- `ole32!PropVariantClear` at `0x18000caa9`
- `ole32!PropVariantClear` at `0x18000cab3`
- `ole32!PropVariantClear` at `0x18000caa9`
- `ole32!PropVariantClear` at `0x18000cab3`
- `ole32!CoTaskMemFree` at `0x18000cad7`
- `ole32!CoTaskMemFree` at `0x18000cad7`

## pseudocode

```c
__int64 __fastcall CPnpNotification::OnUpdate(
        CPnpNotification *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  int v13; // r9d
  struct _RTL_CRITICAL_SECTION *v14; // r12
  _UNKNOWN **v15; // rcx
  __int64 *v16; // rdi
  int v17; // r9d
  struct CChildDeviceInfo *v18; // rdx
  int v19; // r9d
  __int64 v20; // rdx
  int v21; // eax
  bool v22; // cf
  CPnpNotification *v24; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *String2[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h]
  wchar_t *String1[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v30; // [rsp+70h] [rbp-10h]
  int v32; // [rsp+D8h] [rbp+58h]

  v26 = 0;
  v28 = 0;
  v30 = 0;
  pv = 0;
  *(_OWORD *)String2 = 0;
  *(_OWORD *)String1 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v24 = this;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u )
    {
      v9 = 17;
LABEL_82:
      WPP_SF_sqd(v7[2], v9, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
      return v8;
    }
    return v8;
  }
  v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a4->lpVtbl->GetID)(a4, &pv);
  if ( !v8 )
  {
    v32 = 0;
    v28 = 0;
    v30 = 0;
    *(_OWORD *)String2 = 0;
    *(_OWORD *)String1 = 0;
    if ( a2 )
    {
      if ( a2 != QUA_REMOVE )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v12, a2, (__int64)pv);
        v8 = 1;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
          v12,
          (__int64)pv);
      LOWORD(String2[0]) = 31;
      String2[1] = (wchar_t *)pv;
      pv = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
          v12,
          (__int64)pv);
      v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, _QWORD, __int64 *))a4->lpVtbl->OpenPropertyStore)(
             a4,
             0,
             &v26);
      if ( v8 )
        goto LABEL_72;
      v8 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, wchar_t **))(*(_QWORD *)v26 + 40LL))(
             v26,
             &PKEY_PNPX_GlobalIdentity,
             String2);
      if ( v8 )
        goto LABEL_72;
      if ( LOWORD(String2[0]) != 31 || !String2[1] )
        goto LABEL_30;
      v8 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, wchar_t **))(*(_QWORD *)v26 + 40LL))(
             v26,
             &PKEY_PNPX_ID,
             String1);
      if ( v8 )
        goto LABEL_72;
      if ( LOWORD(String1[0]) != 31 || !String1[1] )
      {
LABEL_30:
        v8 = -2147467259;
        goto LABEL_72;
      }
      if ( _wcsicmp(String1[1], String2[1]) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)String2[1], (__int64)String1[1]);
      }
      else
      {
        v32 = 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
            v13,
            (__int64)String2[1]);
      }
    }
    v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
      v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    v16 = (__int64 *)*((_QWORD *)this + 16);
    if ( v16 != (__int64 *)((char *)this + 128) )
    {
      while ( 1 )
      {
        if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 25) >= 4u )
          WPP_SF_sSS((TRACEHANDLE)v15[2], (__int64)String2[1], v16[2]);
        if ( !_wcsicmp(String2[1], (const wchar_t *)v16[2]) && a2 == *((_DWORD *)v16 + 20) )
        {
          if ( a2 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_sS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
                v17,
                (__int64)String2[1]);
            v20 = 1;
            goto LABEL_63;
          }
          if ( v32 )
          {
            if ( !*((_DWORD *)v16 + 15) )
            {
              *((_DWORD *)v16 + 15) = 1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_sS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
                  v17,
                  (__int64)String2[1]);
              (*(void (__fastcall **)(__int64, __int64, _QWORD, wchar_t *, CPnpNotification *))(*(_QWORD *)v16[5] + 40LL))(
                v16[5],
                10001,
                0,
                String2[1],
                v24);
              if ( !*((_DWORD *)v16 + 16) )
              {
LABEL_55:
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_sS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    27,
                    (unsigned int)&WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids,
                    v19,
                    (__int64)String2[1]);
                v20 = 0;
LABEL_63:
                (*(void (__fastcall **)(__int64, __int64, __int64, struct IFunctionInstance *))(*(_QWORD *)v16[5] + 24LL))(
                  v16[5],
                  v20,
                  a3,
                  a4);
                *((_DWORD *)v16 + 14) = 1;
              }
            }
          }
          else
          {
            v18 = (struct CChildDeviceInfo *)v16[9];
            if ( v18 && CPnpNotification::SetChildDeviceInstalled(this, v18, *((_DWORD *)v16 + 16), String1[1]) )
              goto LABEL_55;
          }
        }
        v16 = (__int64 *)*v16;
        if ( v16 == (__int64 *)((char *)this + 128) )
        {
          v8 = 0;
          v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
          break;
        }
        v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
    }
    LeaveCriticalSection(v14);
LABEL_72:
    PropVariantClear((PROPVARIANT *)String1);
    PropVariantClear((PROPVARIANT *)String2);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( pv )
      CoTaskMemFree(pv);
    v7 = WPP_GLOBAL_Control;
    v21 = 0;
    if ( v8 )
      v22 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
    else
      v22 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      LOBYTE(v21) = !v22;
      if ( v21 )
      {
        v9 = 29;
        goto LABEL_82;
      }
    }
    return v8;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 18;
    goto LABEL_82;
  }
  return v8;
}

```

## disassembly

```asm
0x18000c5a0  mov     [rsp-38h+arg_0], rbx
0x18000c5a5  mov     [rsp-38h+arg_10], r8
0x18000c5aa  push    rbp
0x18000c5ab  push    rsi
0x18000c5ac  push    rdi
0x18000c5ad  push    r12
0x18000c5af  push    r13
0x18000c5b1  push    r14
0x18000c5b3  push    r15
0x18000c5b5  mov     rbp, rsp
0x18000c5b8  sub     rsp, 80h
0x18000c5bf  xor     esi, esi
0x18000c5c1  xorps   xmm0, xmm0
0x18000c5c4  xor     eax, eax
0x18000c5c6  mov     [rbp+var_40], rsi
0x18000c5ca  xorps   xmm1, xmm1
0x18000c5cd  mov     [rbp+var_28], rax
0x18000c5d1  mov     [rbp+var_10], rax
0x18000c5d5  mov     r13, r9
0x18000c5d8  mov     r15d, edx
0x18000c5db  mov     [rbp+pv], rsi
0x18000c5df  mov     r14, rcx
0x18000c5e2  movups  xmmword ptr [rbp+String2], xmm0
0x18000c5e6  movups  xmmword ptr [rbp+String1], xmm1
0x18000c5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5f1  lea     r12, WPP_GLOBAL_Control
0x18000c5f8  cmp     rcx, r12
0x18000c5fb  jz      short loc_18000C622
0x18000c5fd  cmp     byte ptr [rcx+19h], 4
0x18000c601  jb      short loc_18000C622
0x18000c603  mov     rcx, [rcx+10h]
0x18000c607  lea     edx, [rsi+10h]
0x18000c60a  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c611  mov     [rsp+80h+var_60], r14
0x18000c616  call    WPP_SF_sq
0x18000c61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c622  test    r13, r13
0x18000c625  jnz     short loc_18000C648
0x18000c627  mov     ebx, 80070057h
0x18000c62c  cmp     rcx, r12
0x18000c62f  jz      loc_18000CB1E
0x18000c635  cmp     byte ptr [rcx+19h], 2
0x18000c639  jb      loc_18000CB1E
0x18000c63f  lea     edx, [r13+11h]
0x18000c643  jmp     loc_18000CB05
0x18000c648  mov     rax, [r13+0]
0x18000c64c  lea     rdx, [rbp+pv]
0x18000c650  mov     rcx, r13
0x18000c653  mov     rax, [rax+20h]
0x18000c657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65c  mov     [rbp+var_50], eax
0x18000c65f  mov     ebx, eax
0x18000c661  test    eax, eax
0x18000c663  jz      short loc_18000C689
0x18000c665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c66c  cmp     rcx, r12
0x18000c66f  jz      loc_18000CB1E
0x18000c675  cmp     byte ptr [rcx+19h], 2
0x18000c679  jb      loc_18000CB1E
0x18000c67f  mov     edx, 12h
0x18000c684  jmp     loc_18000CB05
0x18000c689  xor     eax, eax
0x18000c68b  mov     [rbp+arg_18], esi
0x18000c68e  mov     [rbp+var_28], rax
0x18000c692  xorps   xmm0, xmm0
0x18000c695  mov     [rbp+var_10], rax
0x18000c699  xorps   xmm1, xmm1
0x18000c69c  movups  xmmword ptr [rbp+String2], xmm0
0x18000c6a0  movups  xmmword ptr [rbp+String1], xmm1
0x18000c6a4  test    r15d, r15d
0x18000c6a7  jnz     loc_18000C808
0x18000c6ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6b4  cmp     rcx, r12
0x18000c6b7  jz      short loc_18000C6DB
0x18000c6b9  cmp     byte ptr [rcx+19h], 4
0x18000c6bd  jb      short loc_18000C6DB
0x18000c6bf  mov     rcx, [rcx+10h]
0x18000c6c3  lea     edx, [rax+13h]
0x18000c6c6  mov     rax, [rbp+pv]
0x18000c6ca  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c6d1  mov     [rsp+80h+var_60], rax
0x18000c6d6  call    WPP_SF_sS
0x18000c6db  mov     rax, [r13+0]
0x18000c6df  lea     r8, [rbp+var_40]
0x18000c6e3  xor     edx, edx
0x18000c6e5  mov     rcx, r13
0x18000c6e8  mov     rax, [rax+30h]
0x18000c6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f1  mov     ebx, eax
0x18000c6f3  test    eax, eax
0x18000c6f5  jnz     loc_18000CAA5
0x18000c6fb  mov     rcx, [rbp+var_40]
0x18000c6ff  lea     r8, [rbp+String2]
0x18000c703  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000c70a  mov     rax, [rcx]
0x18000c70d  mov     rax, [rax+28h]
0x18000c711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c716  mov     ebx, eax
0x18000c718  test    eax, eax
0x18000c71a  jnz     loc_18000CAA5
0x18000c720  lea     edi, [rax+1Fh]
0x18000c723  cmp     di, word ptr [rbp+String2]
0x18000c727  jnz     loc_18000C7FE
0x18000c72d  cmp     [rbp+String2+8], rsi
0x18000c731  jz      loc_18000C7FE
0x18000c737  mov     rcx, [rbp+var_40]
0x18000c73b  lea     r8, [rbp+String1]
0x18000c73f  lea     rdx, PKEY_PNPX_ID
0x18000c746  mov     rax, [rcx]
0x18000c749  mov     rax, [rax+28h]
0x18000c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c752  mov     [rbp+var_50], eax
0x18000c755  mov     ebx, eax
0x18000c757  test    eax, eax
0x18000c759  jnz     loc_18000CAA5
0x18000c75f  cmp     di, word ptr [rbp+String1]
0x18000c763  jnz     loc_18000C7FE
0x18000c769  mov     rcx, [rbp+String1+8]; String1
0x18000c76d  test    rcx, rcx
0x18000c770  jz      loc_18000C7FE
0x18000c776  mov     rdx, [rbp+String2+8]; String2
0x18000c77a  call    cs:__imp__wcsicmp
0x18000c780  test    eax, eax
0x18000c782  jnz     short loc_18000C7C6
0x18000c784  mov     [rbp+arg_18], 1
0x18000c78b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c792  cmp     rcx, r12
0x18000c795  jz      loc_18000C856
0x18000c79b  cmp     byte ptr [rcx+19h], 4
0x18000c79f  jb      loc_18000C856
0x18000c7a5  mov     rax, [rbp+String2+8]
0x18000c7a9  lea     edx, [rdi-0Bh]
0x18000c7ac  mov     rcx, [rcx+10h]
0x18000c7b0  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c7b7  mov     [rsp+80h+var_60], rax
0x18000c7bc  call    WPP_SF_sS
0x18000c7c1  jmp     loc_18000C856
0x18000c7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7cd  cmp     rcx, r12
0x18000c7d0  jz      loc_18000C856
0x18000c7d6  cmp     byte ptr [rcx+19h], 4
0x18000c7da  jb      short loc_18000C856
0x18000c7dc  mov     rax, [rbp+String1+8]
0x18000c7e0  mov     edx, 15h
0x18000c7e5  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c7e9  mov     [rsp+80h+var_58], rax; __int64
0x18000c7ee  mov     rax, [rbp+String2+8]
0x18000c7f2  mov     [rsp+80h+var_60], rax; __int64
0x18000c7f7  call    WPP_SF_sSS
0x18000c7fc  jmp     short loc_18000C856
0x18000c7fe  mov     ebx, 80004005h
0x18000c803  jmp     loc_18000CAA5
0x18000c808  cmp     r15d, 1
0x18000c80c  jnz     loc_18000CA77
0x18000c812  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c819  cmp     rcx, r12
0x18000c81c  jz      short loc_18000C841
0x18000c81e  cmp     byte ptr [rcx+19h], 4
0x18000c822  jb      short loc_18000C841
0x18000c824  mov     rax, [rbp+pv]
0x18000c828  lea     edx, [r15+15h]
0x18000c82c  mov     rcx, [rcx+10h]
0x18000c830  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c837  mov     [rsp+80h+var_60], rax
0x18000c83c  call    WPP_SF_sS
0x18000c841  mov     rax, [rbp+pv]
0x18000c845  mov     edi, 1Fh
0x18000c84a  mov     word ptr [rbp+String2], di
0x18000c84e  mov     [rbp+String2+8], rax
0x18000c852  mov     [rbp+pv], rsi
0x18000c856  lea     r12, [r14+48h]
0x18000c85a  mov     rcx, r12; lpCriticalSection
0x18000c85d  call    cs:__imp_EnterCriticalSection
0x18000c863  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c86a  lea     rax, WPP_GLOBAL_Control
0x18000c871  cmp     rcx, rax
0x18000c874  jz      short loc_18000C89F
0x18000c876  cmp     byte ptr [rcx+19h], 4
0x18000c87a  jb      short loc_18000C89F
0x18000c87c  mov     rcx, [rcx+10h]
0x18000c880  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c887  mov     edx, 18h
0x18000c88c  call    WPP_SF_s
0x18000c891  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c898  lea     rax, WPP_GLOBAL_Control
0x18000c89f  lea     rsi, [r14+80h]
0x18000c8a6  mov     rdi, [rsi]
0x18000c8a9  cmp     rdi, rsi
0x18000c8ac  jz      loc_18000CA63
0x18000c8b2  mov     r12d, [rbp+arg_18]
0x18000c8b6  mov     rbx, [rbp+arg_10]
0x18000c8ba  cmp     rcx, rax
0x18000c8bd  jz      short loc_18000C8E5
0x18000c8bf  cmp     byte ptr [rcx+19h], 4
0x18000c8c3  jb      short loc_18000C8E5
0x18000c8c5  mov     rax, [rdi+10h]
0x18000c8c9  mov     edx, 19h
0x18000c8ce  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c8d2  mov     [rsp+80h+var_58], rax; __int64
0x18000c8d7  mov     rax, [rbp+String2+8]
0x18000c8db  mov     [rsp+80h+var_60], rax; __int64
0x18000c8e0  call    WPP_SF_sSS
0x18000c8e5  mov     rdx, [rdi+10h]; String2
0x18000c8e9  mov     rcx, [rbp+String2+8]; String1
0x18000c8ed  call    cs:__imp__wcsicmp
0x18000c8f3  test    eax, eax
0x18000c8f5  jnz     loc_18000CA41
0x18000c8fb  cmp     r15d, [rdi+50h]
0x18000c8ff  jnz     loc_18000CA41
0x18000c905  test    r15d, r15d
0x18000c908  jnz     loc_18000C9E3
0x18000c90e  test    r12d, r12d
0x18000c911  jnz     short loc_18000C93A
0x18000c913  mov     rdx, [rdi+48h]; struct CChildDeviceInfo *
0x18000c917  test    rdx, rdx
0x18000c91a  jz      loc_18000CA41
0x18000c920  mov     r9, [rbp+String1+8]; unsigned __int16 *
0x18000c924  mov     rcx, r14; this
0x18000c927  mov     r8d, [rdi+40h]; unsigned int
0x18000c92b  call    ?SetChildDeviceInstalled@CPnpNotification@@IEAAHPEAVCChildDeviceInfo@@KPEBG@Z; CPnpNotification::SetChildDeviceInstalled(CChildDeviceInfo *,ulong,ushort const *)
0x18000c930  test    eax, eax
0x18000c932  jz      loc_18000CA41
0x18000c938  jmp     short loc_18000C9A8
0x18000c93a  cmp     dword ptr [rdi+3Ch], 0
0x18000c93e  jnz     loc_18000CA41
0x18000c944  mov     dword ptr [rdi+3Ch], 1
0x18000c94b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c952  lea     rax, WPP_GLOBAL_Control
0x18000c959  cmp     rcx, rax
0x18000c95c  jz      short loc_18000C982
0x18000c95e  cmp     byte ptr [rcx+19h], 4
0x18000c962  jb      short loc_18000C982
0x18000c964  mov     rax, [rbp+String2+8]
0x18000c968  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c96f  mov     rcx, [rcx+10h]
0x18000c973  mov     edx, 1Ah
0x18000c978  mov     [rsp+80h+var_60], rax
0x18000c97d  call    WPP_SF_sS
0x18000c982  mov     rcx, [rdi+28h]
0x18000c986  xor     r8d, r8d
0x18000c989  mov     r9, [rbp+String2+8]
0x18000c98d  mov     edx, 2711h
0x18000c992  mov     rax, [rcx]
0x18000c995  mov     rax, [rax+28h]
0x18000c999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c99e  cmp     dword ptr [rdi+40h], 0
0x18000c9a2  jnz     loc_18000CA41
0x18000c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9af  lea     rax, WPP_GLOBAL_Control
0x18000c9b6  cmp     rcx, rax
0x18000c9b9  jz      short loc_18000C9DF
0x18000c9bb  cmp     byte ptr [rcx+19h], 4
0x18000c9bf  jb      short loc_18000C9DF
0x18000c9c1  mov     rax, [rbp+String2+8]
0x18000c9c5  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c9cc  mov     rcx, [rcx+10h]
0x18000c9d0  mov     edx, 1Bh
0x18000c9d5  mov     [rsp+80h+var_60], rax
0x18000c9da  call    WPP_SF_sS
0x18000c9df  xor     edx, edx
0x18000c9e1  jmp     short loc_18000CA24
0x18000c9e3  cmp     r15d, 1
0x18000c9e7  jnz     short loc_18000CA41
0x18000c9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9f0  lea     rax, WPP_GLOBAL_Control
0x18000c9f7  cmp     rcx, rax
0x18000c9fa  jz      short loc_18000CA1F
0x18000c9fc  cmp     byte ptr [rcx+19h], 4
0x18000ca00  jb      short loc_18000CA1F
0x18000ca02  mov     rax, [rbp+String2+8]
0x18000ca06  lea     edx, [r15+1Bh]
0x18000ca0a  mov     rcx, [rcx+10h]
0x18000ca0e  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000ca15  mov     [rsp+80h+var_60], rax
0x18000ca1a  call    WPP_SF_sS
0x18000ca1f  mov     edx, 1
0x18000ca24  mov     rcx, [rdi+28h]
0x18000ca28  mov     r9, r13
0x18000ca2b  mov     r8, rbx
0x18000ca2e  mov     rax, [rcx]
0x18000ca31  mov     rax, [rax+18h]
0x18000ca35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca3a  mov     dword ptr [rdi+38h], 1
0x18000ca41  mov     rdi, [rdi]
0x18000ca44  cmp     rdi, rsi
0x18000ca47  jz      short loc_18000CA5C
0x18000ca49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca50  lea     rax, WPP_GLOBAL_Control
0x18000ca57  jmp     loc_18000C8BA
0x18000ca5c  mov     ebx, [rbp+var_50]
0x18000ca5f  lea     r12, [r14+48h]
0x18000ca63  mov     rcx, r12; lpCriticalSection
0x18000ca66  call    cs:__imp_LeaveCriticalSection
0x18000ca6c  xor     esi, esi
0x18000ca6e  lea     r12, WPP_GLOBAL_Control
0x18000ca75  jmp     short loc_18000CAA5
0x18000ca77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca7e  cmp     rcx, r12
0x18000ca81  jz      short loc_18000CAA0
0x18000ca83  cmp     byte ptr [rcx+19h], 4
  ... truncated ...
```

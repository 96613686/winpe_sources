# PROPVARIANT2DEVPROP(tagPROPVARIANT &,_DEVPROPERTY *)

- ea: `0x180058dbc`
- end: `0x1800593a7`
- name: `?PROPVARIANT2DEVPROP@@YAJAEAUtagPROPVARIANT@@PEAU_DEVPROPERTY@@@Z`
- size: `1515`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, struct _DEVPROPERTY *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003de0`
- `0x18000dd00`
- `0x18000e650`

## callees

- `0x18001b950`
- `0x18001ba30`
- `0x18001f2b0`
- `0x180026500`
- `0x180029024`
- `0x180034c5c`
- `0x18003f78c`
- `0x180058dbc`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180058e79`
- `OLEAUT32!__imp_SysStringLen` at `0x180058e79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058e8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058f47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800591b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058f47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800591b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005924c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005924c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PROPVARIANT2DEVPROP(PROPVARIANT *pvar, struct _DEVPROPERTY *a2)
{
  unsigned int v4; // edi
  PROPVARIANT *v5; // r14
  unsigned int v6; // r9d
  char *v7; // rax
  size_t v8; // rdi
  SIZE_T v9; // r12
  _WORD *v10; // rax
  _WORD *v11; // rbx
  size_t v12; // rdi
  __int64 v13; // rax
  _WORD *v14; // rcx
  SIZE_T v15; // r8
  void *v16; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r12
  unsigned int v21; // r10d
  void *v22; // rcx
  int v23; // r10d
  unsigned __int8 v24; // r11
  int v25; // ebx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  unsigned __int64 v29; // rdx
  __int64 v30; // rbx
  ULONG v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // [rsp+28h] [rbp-28h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  void *v35; // [rsp+38h] [rbp-18h] BYREF
  char v36; // [rsp+40h] [rbp-10h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v38; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int64 v39; // [rsp+A0h] [rbp+50h] BYREF

  v4 = 0;
  v5 = pvar + 1;
  a2->Buffer = pvar + 1;
  a2->CompKey.Store = DEVPROP_STORE_SYSTEM;
  a2->CompKey.LocaleName = 0;
  v6 = *(unsigned __int16 *)pvar;
  if ( v6 > 0x15 )
  {
    switch ( v6 )
    {
      case 0x1Fu:
        a2->Type = 18;
        v32 = -1;
        do
          ++v32;
        while ( *((_WORD *)*v5 + v32) );
        a2->BufferSize = 2 * v32 + 2;
        a2->Buffer = *v5;
        return v4;
      case 0x40u:
        a2->Type = 16;
        goto LABEL_38;
      case 0x41u:
        a2->Type = 4099;
        v31 = *(_DWORD *)v5;
        break;
      case 0x48u:
        a2->Type = 13;
        a2->BufferSize = 16;
        v7 = (char *)*v5;
        goto LABEL_13;
      case 0x1003u:
        if ( !*(_DWORD *)v5 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)-2147418113;
          }
          v19 = 15;
          goto LABEL_31;
        }
        a2->Type = 4102;
        v31 = 4 * *(_DWORD *)v5;
        break;
      default:
        v19 = 14;
        if ( v6 == 4113 )
        {
          if ( *(_DWORD *)v5 )
          {
            a2->Type = 4099;
            a2->BufferSize = *(_DWORD *)v5;
            a2->Buffer = pvar[2];
            return v4;
          }
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)-2147418113;
          }
        }
        else
        {
          if ( v6 != 4127 )
          {
LABEL_46:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
            }
            return (unsigned int)-2147418113;
          }
          if ( *(_DWORD *)v5 )
          {
            v20 = 2;
            pv = 0;
            v21 = 0;
            while ( 1 )
            {
              v38 = 0;
              if ( (int)StringCbLengthW(
                          *((const unsigned __int16 **)pvar[2] + v21),
                          0x7FFFFFFFu,
                          (unsigned __int64 *)&v38) < 0 )
                break;
              v20 += (__int64)(v38 + 1);
              v21 = v23 + 1;
              if ( v21 >= *(_DWORD *)v5 )
              {
                p_pv = &pv;
                v35 = 0;
                v36 = 1;
                v25 = CTCoAllocPolicy::Alloc(v22, 1u, v20, &v35);
                wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
                if ( v25 >= 0 )
                {
                  v28 = (unsigned __int16 *)pv;
                  v38 = (unsigned __int16 *)pv;
                  v29 = v20;
                  v39 = v20;
                  v30 = 0;
                  if ( !*(_DWORD *)v5 )
                  {
LABEL_66:
                    a2->Type = 8210;
                    a2->BufferSize = v20;
                    a2->Buffer = v28;
                    PropVariantClear(pvar);
                    *(_WORD *)pvar = 31;
                    pvar[1] = pv;
                    return v4;
                  }
                  while ( (int)StringCbCopyExW(v28, v29, *((const unsigned __int16 **)pvar[2] + v30), &v38, &v39, v33) >= 0 )
                  {
                    v28 = ++v38;
                    v29 = v39 - 2;
                    v39 -= 2LL;
                    v30 = (unsigned int)(v30 + 1);
                    if ( (unsigned int)v30 >= *((_DWORD *)pvar + 2) )
                    {
                      v28 = (unsigned __int16 *)pv;
                      goto LABEL_66;
                    }
                  }
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v27 = 18;
LABEL_60:
                    WPP_SF_(v26[2], v27, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
                  }
                }
                else
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v27 = 17;
                    goto LABEL_60;
                  }
                }
                v4 = -2147418113;
                v16 = pv;
                pv = 0;
                goto LABEL_76;
              }
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= v24 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
            }
            v4 = -2147418113;
            v16 = pv;
            pv = 0;
LABEL_76:
            if ( !v16 )
              return v4;
            goto LABEL_77;
          }
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)-2147418113;
          }
          v19 = 19;
        }
LABEL_31:
        WPP_SF_(v18[2], v19, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
        return (unsigned int)-2147418113;
    }
    a2->BufferSize = v31;
    v7 = (char *)pvar[2];
    goto LABEL_13;
  }
  if ( v6 == 21 )
  {
    a2->Type = 9;
    goto LABEL_38;
  }
  if ( !*(_WORD *)pvar )
  {
    *(_QWORD *)&a2->Type = 0;
    a2->Buffer = 0;
    return v4;
  }
  switch ( v6 )
  {
    case 2u:
      a2->Type = 4;
      a2->BufferSize = 2;
      return v4;
    case 3u:
      a2->Type = 6;
      goto LABEL_34;
    case 5u:
      a2->Type = 11;
LABEL_38:
      a2->BufferSize = 8;
      return v4;
  }
  if ( v6 != 8 )
  {
    if ( v6 != 11 )
    {
      if ( v6 == 19 )
      {
        a2->Type = 7;
LABEL_34:
        a2->BufferSize = 4;
        return v4;
      }
      goto LABEL_46;
    }
    a2->Type = 17;
    a2->BufferSize = 1;
    v7 = &byte_18007103A;
    if ( *(_BYTE *)v5 )
      v7 = byte_18007103B;
LABEL_13:
    a2->Buffer = v7;
    return v4;
  }
  v8 = SysStringLen((BSTR)*v5) + 1;
  v9 = (unsigned int)(2 * v8 + 2);
  v10 = CoTaskMemAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    v19 = 12;
    goto LABEL_31;
  }
  v12 = v8;
  memcpy_0(v10, *v5, v12 * 2);
  v11[v12] = 0;
  v13 = 0;
  v14 = v11;
  if ( v9 < 2 )
  {
LABEL_21:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
    v4 = -2147418113;
    v16 = v11;
LABEL_77:
    CoTaskMemFree(v16);
    return v4;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v13 += 2;
      v15 = v13 + 2;
      if ( !*v14 && v15 <= v9 )
        break;
      ++v14;
      if ( v15 > v9 )
        goto LABEL_21;
    }
    if ( !v14[1] )
      break;
    ++v14;
  }
  a2->Type = 8210;
  a2->Buffer = v11;
  a2->BufferSize = v13 + 2;
  PropVariantClear(pvar);
  *(_WORD *)pvar = 31;
  *v5 = v11;
  return 0;
}

```

## disassembly

```asm
0x180058dbc  mov     [rsp-38h+arg_18], rbx
0x180058dc1  push    rbp
0x180058dc2  push    rsi
0x180058dc3  push    rdi
0x180058dc4  push    r12
0x180058dc6  push    r13
0x180058dc8  push    r14
0x180058dca  push    r15
0x180058dcc  mov     rbp, rsp
0x180058dcf  sub     rsp, 50h
0x180058dd3  mov     rsi, rdx
0x180058dd6  mov     r15, rcx
0x180058dd9  xor     ebx, ebx
0x180058ddb  mov     edi, ebx
0x180058ddd  lea     r14, [rcx+8]
0x180058de1  mov     [rdx+28h], r14
0x180058de5  mov     [rdx+14h], ebx
0x180058de8  mov     [rdx+18h], rbx
0x180058dec  movzx   r9d, word ptr [rcx]
0x180058df0  lea     r11d, [rbx+2]
0x180058df4  cmp     r9d, 15h
0x180058df8  ja      loc_180058FF1
0x180058dfe  jz      loc_180058FDE
0x180058e04  mov     ecx, r9d
0x180058e07  test    r9d, r9d
0x180058e0a  jz      loc_180058FD1
0x180058e10  sub     ecx, r11d
0x180058e13  jz      loc_180058FC1
0x180058e19  sub     ecx, 1
0x180058e1c  jz      loc_180058FAE
0x180058e22  sub     ecx, r11d
0x180058e25  jz      loc_180058FA5
0x180058e2b  sub     ecx, 3
0x180058e2e  jz      short loc_180058E76
0x180058e30  sub     ecx, 3
0x180058e33  jz      short loc_180058E4A
0x180058e35  cmp     ecx, 8
0x180058e38  jnz     loc_18005903A
0x180058e3e  mov     dword ptr [rdx+20h], 7
0x180058e45  jmp     loc_180058FB5
0x180058e4a  mov     dword ptr [rdx+20h], 11h
0x180058e51  mov     dword ptr [rdx+24h], 1
0x180058e58  lea     rcx, byte_18007103B
0x180058e5f  lea     rax, byte_18007103A
0x180058e66  cmp     [r14], bl
0x180058e69  cmovnz  rax, rcx
0x180058e6d  mov     [rdx+28h], rax
0x180058e71  jmp     loc_18005938D
0x180058e76  mov     rcx, [r14]; pbstr
0x180058e79  call    cs:__imp_SysStringLen
0x180058e7f  lea     edi, [rax+1]
0x180058e82  lea     eax, ds:2[rdi*2]
0x180058e89  mov     r12d, eax
0x180058e8c  mov     ecx, eax; cb
0x180058e8e  call    cs:__imp_CoTaskMemAlloc
0x180058e94  mov     rbx, rax
0x180058e97  xor     r13d, r13d
0x180058e9a  test    rax, rax
0x180058e9d  jz      loc_180058F5D
0x180058ea3  add     rdi, rdi
0x180058ea6  mov     r8, rdi; Size
0x180058ea9  mov     rdx, [r14]; Src
0x180058eac  mov     rcx, rax; void *
0x180058eaf  call    memcpy_0
0x180058eb4  mov     [rbx+rdi], r13w
0x180058eb9  mov     eax, r13d
0x180058ebc  mov     rcx, rbx
0x180058ebf  cmp     r12, 2
0x180058ec3  jb      short loc_180058EEF
0x180058ec5  add     rax, 2
0x180058ec9  lea     rdx, [rcx+2]
0x180058ecd  lea     r8, [rax+2]
0x180058ed1  cmp     [rcx], r13w
0x180058ed5  jnz     short loc_180058EE7
0x180058ed7  cmp     r8, r12
0x180058eda  ja      short loc_180058EE7
0x180058edc  cmp     [rdx], r13w
0x180058ee0  jz      short loc_180058F33
0x180058ee2  mov     rcx, rdx
0x180058ee5  jmp     short loc_180058EC5
0x180058ee7  mov     rcx, rdx
0x180058eea  cmp     r8, r12
0x180058eed  jbe     short loc_180058EC5
0x180058eef  lea     rax, WPP_GLOBAL_Control
0x180058ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180058efd  cmp     rcx, rax
0x180058f00  jz      short loc_180058F26
0x180058f02  test    dword ptr [rcx+1Ch], 80000h
0x180058f09  jz      short loc_180058F26
0x180058f0b  cmp     byte ptr [rcx+19h], 2
0x180058f0f  jb      short loc_180058F26
0x180058f11  mov     edx, 0Dh
0x180058f16  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180058f1d  mov     rcx, [rcx+10h]
0x180058f21  call    WPP_SF_
0x180058f26  mov     edi, 8000FFFFh
0x180058f2b  mov     rcx, rbx
0x180058f2e  jmp     loc_18005924C
0x180058f33  mov     dword ptr [rsi+20h], 2012h
0x180058f3a  mov     [rsi+28h], rbx
0x180058f3e  add     eax, 2
0x180058f41  mov     [rsi+24h], eax
0x180058f44  mov     rcx, r15; pvar
0x180058f47  call    cs:__imp_PropVariantClear
0x180058f4d  mov     word ptr [r15], 1Fh
0x180058f53  mov     [r14], rbx
0x180058f56  xor     eax, eax
0x180058f58  jmp     loc_18005938F
0x180058f5d  lea     rax, WPP_GLOBAL_Control
0x180058f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f6b  cmp     rcx, rax
0x180058f6e  jz      loc_180059071
0x180058f74  test    dword ptr [rcx+1Ch], 80000h
0x180058f7b  jz      loc_180059071
0x180058f81  cmp     byte ptr [rcx+19h], 2
0x180058f85  jb      loc_180059071
0x180058f8b  mov     edx, 0Ch
0x180058f90  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180058f97  mov     rcx, [rcx+10h]
0x180058f9b  call    WPP_SF_
0x180058fa0  jmp     loc_180059071
0x180058fa5  mov     dword ptr [rdx+20h], 0Bh
0x180058fac  jmp     short loc_180058FE5
0x180058fae  mov     dword ptr [rdx+20h], 6
0x180058fb5  mov     dword ptr [rdx+24h], 4
0x180058fbc  jmp     loc_18005938D
0x180058fc1  mov     dword ptr [rdx+20h], 4
0x180058fc8  mov     [rdx+24h], r11d
0x180058fcc  jmp     loc_18005938D
0x180058fd1  mov     [rdx+20h], rbx
0x180058fd5  mov     [rdx+28h], rbx
0x180058fd9  jmp     loc_18005938D
0x180058fde  mov     dword ptr [rdx+20h], 9
0x180058fe5  mov     dword ptr [rdx+24h], 8
0x180058fec  jmp     loc_18005938D
0x180058ff1  mov     ecx, r9d
0x180058ff4  mov     r13d, 1Fh
0x180058ffa  sub     ecx, r13d
0x180058ffd  jz      loc_180059365
0x180059003  sub     ecx, 21h ; '!'
0x180059006  jz      loc_180059359
0x18005900c  sub     ecx, 1
0x18005900f  jz      loc_180059343
0x180059015  sub     ecx, 7
0x180059018  jz      loc_18005932D
0x18005901e  sub     ecx, 0FBBh
0x180059024  jz      loc_1800592E1
0x18005902a  lea     edx, [r13-11h]
0x18005902e  sub     ecx, edx
0x180059030  jz      loc_18005928F
0x180059036  cmp     ecx, edx
0x180059038  jz      short loc_18005907B
0x18005903a  lea     rax, WPP_GLOBAL_Control
0x180059041  mov     rcx, cs:WPP_GLOBAL_Control
0x180059048  cmp     rcx, rax
0x18005904b  jz      short loc_180059071
0x18005904d  test    dword ptr [rcx+1Ch], 80000h
0x180059054  jz      short loc_180059071
0x180059056  cmp     [rcx+19h], r11b
0x18005905a  jb      short loc_180059071
0x18005905c  mov     edx, 14h
0x180059061  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180059068  mov     rcx, [rcx+10h]
0x18005906c  call    WPP_SF_d
0x180059071  mov     edi, 8000FFFFh
0x180059076  jmp     loc_18005938D
0x18005907b  cmp     [r14], ebx
0x18005907e  jbe     loc_180059257
0x180059084  mov     r12, r11
0x180059087  mov     [rbp+pv], rbx
0x18005908b  mov     r10d, ebx
0x18005908e  mov     [rbp+arg_8], rbx
0x180059092  mov     eax, r10d
0x180059095  mov     rcx, [r15+10h]
0x180059099  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18005909d  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800590a2  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x1800590a6  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800590ab  test    eax, eax
0x1800590ad  js      loc_1800591FF
0x1800590b3  mov     rax, [rbp+arg_8]
0x1800590b7  add     rax, 2
0x1800590bb  add     r12, rax
0x1800590be  inc     r10d
0x1800590c1  cmp     r10d, [r14]
0x1800590c4  jb      short loc_18005908E
0x1800590c6  lea     rax, [rbp+pv]
0x1800590ca  mov     [rbp+var_20], rax
0x1800590ce  mov     [rbp+var_18], rbx
0x1800590d2  mov     [rbp+var_10], 1
0x1800590d6  lea     r9, [rbp+var_18]; void **
0x1800590da  mov     r8, r12; unsigned __int64
0x1800590dd  mov     edx, 1; unsigned int
0x1800590e2  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800590e7  mov     ebx, eax
0x1800590e9  lea     rcx, [rbp+var_20]
0x1800590ed  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800590f2  shr     ebx, 1Fh
0x1800590f5  test    bl, bl
0x1800590f7  jz      short loc_180059146
0x1800590f9  lea     rax, WPP_GLOBAL_Control
0x180059100  mov     rcx, cs:WPP_GLOBAL_Control
0x180059107  cmp     rcx, rax
0x18005910a  jz      short loc_180059130
0x18005910c  test    dword ptr [rcx+1Ch], 80000h
0x180059113  jz      short loc_180059130
0x180059115  cmp     byte ptr [rcx+19h], 2
0x180059119  jb      short loc_180059130
0x18005911b  mov     edx, 11h
0x180059120  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180059127  mov     rcx, [rcx+10h]
0x18005912b  call    WPP_SF_
0x180059130  mov     edi, 8000FFFFh
0x180059135  mov     rcx, [rbp+pv]
0x180059139  mov     [rbp+pv], 0
0x180059141  jmp     loc_180059243
0x180059146  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18005914a  mov     [rbp+arg_8], rcx
0x18005914e  mov     rdx, r12; unsigned __int64
0x180059151  mov     [rbp+arg_10], rdx
0x180059155  xor     ebx, ebx
0x180059157  cmp     [r14], ebx
0x18005915a  jbe     short loc_18005919E
0x18005915c  mov     r8, [r15+10h]
0x180059160  lea     r9, [rbp+arg_10]
0x180059164  mov     [rsp+50h+var_30], r9; unsigned __int64 *
0x180059169  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x18005916d  mov     r8, [r8+rbx*8]; unsigned __int16 *
0x180059171  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180059176  test    eax, eax
0x180059178  js      short loc_1800591C7
0x18005917a  mov     rcx, [rbp+arg_8]
0x18005917e  add     rcx, 2
0x180059182  mov     [rbp+arg_8], rcx
0x180059186  mov     rdx, [rbp+arg_10]
0x18005918a  sub     rdx, 2
0x18005918e  mov     [rbp+arg_10], rdx
0x180059192  inc     ebx
0x180059194  cmp     ebx, [r15+8]
0x180059198  jb      short loc_18005915C
0x18005919a  mov     rcx, [rbp+pv]
0x18005919e  mov     dword ptr [rsi+20h], 2012h
0x1800591a5  mov     [rsi+24h], r12d
0x1800591a9  mov     [rsi+28h], rcx
0x1800591ad  mov     rcx, r15; pvar
0x1800591b0  call    cs:__imp_PropVariantClear
0x1800591b6  mov     [r15], r13w
0x1800591ba  mov     rax, [rbp+pv]
0x1800591be  mov     [r15+8], rax
0x1800591c2  jmp     loc_18005938D
0x1800591c7  lea     rax, WPP_GLOBAL_Control
0x1800591ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591d5  cmp     rcx, rax
0x1800591d8  jz      loc_180059130
0x1800591de  test    dword ptr [rcx+1Ch], 80000h
0x1800591e5  jz      loc_180059130
0x1800591eb  cmp     byte ptr [rcx+19h], 2
0x1800591ef  jb      loc_180059130
0x1800591f5  mov     edx, 12h
0x1800591fa  jmp     loc_180059120
0x1800591ff  lea     rax, WPP_GLOBAL_Control
0x180059206  mov     rcx, cs:WPP_GLOBAL_Control
0x18005920d  cmp     rcx, rax
0x180059210  jz      short loc_180059236
0x180059212  test    dword ptr [rcx+1Ch], 80000h
0x180059219  jz      short loc_180059236
0x18005921b  cmp     [rcx+19h], r11b
0x18005921f  jb      short loc_180059236
0x180059221  mov     edx, 10h
0x180059226  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18005922d  mov     rcx, [rcx+10h]
0x180059231  call    WPP_SF_
0x180059236  mov     edi, 8000FFFFh
0x18005923b  mov     rcx, [rbp+pv]; pv
0x18005923f  mov     [rbp+pv], rbx
0x180059243  test    rcx, rcx
0x180059246  jz      loc_18005938D
0x18005924c  call    cs:__imp_CoTaskMemFree
0x180059252  jmp     loc_18005938D
0x180059257  lea     rax, WPP_GLOBAL_Control
0x18005925e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059265  cmp     rcx, rax
0x180059268  jz      loc_180059071
0x18005926e  test    dword ptr [rcx+1Ch], 80000h
0x180059275  jz      loc_180059071
0x18005927b  cmp     [rcx+19h], r11b
0x18005927f  jb      loc_180059071
0x180059285  mov     edx, 13h
0x18005928a  jmp     loc_180058F90
0x18005928f  cmp     [r14], ebx
0x180059292  jbe     short loc_1800592AE
0x180059294  mov     dword ptr [rsi+20h], 1003h
0x18005929b  mov     eax, [r14]
0x18005929e  mov     [rsi+24h], eax
0x1800592a1  mov     rax, [r15+10h]
0x1800592a5  mov     [rsi+28h], rax
0x1800592a9  jmp     loc_18005938D
0x1800592ae  lea     rax, WPP_GLOBAL_Control
0x1800592b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592bc  cmp     rcx, rax
  ... truncated ...
```

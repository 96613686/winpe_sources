# _GetGmsaPasswordForKeyID(void *,void *,uchar *,ulong,uchar *,ulong)

- ea: `0x180017030`
- end: `0x1800172c1`
- name: `?_GetGmsaPasswordForKeyID@@YAJPEAX0PEAEK1K@Z`
- size: `657`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800172f0`

## callees

- `0x180010950`
- `0x180010980`
- `0x180016b30`
- `0x180017030`
- `0x180017390`
- `0x180019274`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180017108`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180017108`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800170d3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800170d3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001711d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001711d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017207`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017207`
- `api-ms-win-security-base-private-l1-1-0!IsValidRelativeSecurityDescriptor` at `0x180017130`
- `api-ms-win-security-base-private-l1-1-0!IsValidRelativeSecurityDescriptor` at `0x180017130`

## string_xrefs

- `0x1800170e3`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x1800171e3`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x18001724c`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`
- `0x180017269`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`

## pseudocode

```c
__int64 __fastcall _GetGmsaPasswordForKeyID(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  _BYTE *v6; // rdi
  unsigned int v8; // esi
  __int64 v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // ebx
  DWORD SecurityDescriptorLength; // esi
  struct _KEK_KEY_INFO *v16; // rdi
  __int64 v17; // rcx
  unsigned __int16 *v18; // r9
  __int64 v19; // rdx
  signed int KeyFromKdsService; // eax
  DWORD LengthSid; // eax
  struct _KEK_KEY_INFO *v22; // r8
  signed int GmsaPassword; // eax
  __int64 v24; // rax
  _BYTE *v25; // rcx
  unsigned int v27; // [rsp+70h] [rbp-29h] BYREF
  void *lpMem; // [rsp+78h] [rbp-21h] BYREF
  struct _KEK_KEY_INFO *v29; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v30[10]; // [rsp+90h] [rbp-9h] BYREF

  v6 = 0;
  v8 = 0;
  lpMem = 0;
  v27 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v30[0] = a3;
    v30[1] = a4;
    WPP_SF__HEX_(v12, 10, WPP_e90ce2bd0edb3ab6daae4ad923eb703f_Traceguids, v30);
  }
  if ( a5 && a1 && a2 && a6 )
  {
    if ( !IsValidSid(a2) )
    {
      v13 = 393;
LABEL_10:
      v14 = -2147024809;
      SidKeyDebugTraceError(0x80070057, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx", v13);
      return v14;
    }
    if ( !IsValidSecurityDescriptor(a1) )
    {
      v13 = 401;
      goto LABEL_10;
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(a1);
    if ( !(unsigned int)IsValidRelativeSecurityDescriptor(a1, SecurityDescriptorLength, 5) )
    {
      v13 = 414;
      goto LABEL_10;
    }
    v14 = ValidateClientKEKInfo(a3, a4, &v29);
    if ( (v14 & 0x80000000) != 0 )
      return v14;
    v16 = v29;
    v17 = *((unsigned int *)v29 + 10);
    v18 = (unsigned __int16 *)((char *)v29 + v17 + 52);
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    KeyFromKdsService = GetKeyFromKdsService(
                          a1,
                          SecurityDescriptorLength,
                          (struct _GUID *)((char *)v29 + 24),
                          *((_DWORD *)v29 + 3),
                          *((_DWORD *)v29 + 4),
                          *((_DWORD *)v29 + 5),
                          0,
                          0,
                          v18,
                          2 * (int)v19 + 2,
                          (unsigned __int16 *)((char *)v29 + *((unsigned int *)v29 + 11) + v17 + 52),
                          (unsigned __int8 **)&lpMem,
                          &v27);
    v14 = KeyFromKdsService;
    if ( KeyFromKdsService >= 0 )
    {
      LengthSid = GetLengthSid(a2);
      v22 = v16;
      v6 = lpMem;
      v8 = v27;
      GmsaPassword = _GenerateGmsaPassword((struct _SID_KEY_HEADER *)lpMem, v27, v22, a2, LengthSid, 0, 0, a5, a6);
      v14 = GmsaPassword;
      if ( GmsaPassword < 0 )
        SidKeyDebugTraceError(
          GmsaPassword,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
          0x1D3u);
    }
    else
    {
      SidKeyDebugTraceError(
        KeyFromKdsService,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
        0x1C2u);
      v6 = lpMem;
      v8 = v27;
    }
  }
  else
  {
    v14 = -2147024809;
    SidKeyDebugTraceError(
      0x80070057,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx",
      0x182u);
  }
  if ( v6 )
  {
    v24 = v8;
    v25 = v6;
    if ( v8 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    SIDKeyProvFree(v6);
  }
  return v14;
}

```

## disassembly

```asm
0x180017030  push    rbp
0x180017032  push    rbx
0x180017033  push    rsi
0x180017034  push    rdi
0x180017035  push    r12
0x180017037  push    r13
0x180017039  push    r14
0x18001703b  push    r15
0x18001703d  lea     rbp, [rsp-0Fh]
0x180017042  sub     rsp, 0A8h
0x180017049  xor     edi, edi
0x18001704b  mov     ebx, r9d
0x18001704e  xor     esi, esi
0x180017050  mov     [rbp+47h+lpMem], rdi
0x180017054  mov     [rbp+47h+var_70], esi
0x180017057  mov     r12, r8
0x18001705a  mov     [rbp+47h+var_60], rsi
0x18001705e  mov     r15, rdx
0x180017061  mov     r14, rcx
0x180017064  mov     rcx, cs:WPP_GLOBAL_Control
0x18001706b  lea     rax, WPP_GLOBAL_Control
0x180017072  cmp     rcx, rax
0x180017075  jz      short loc_1800170A7
0x180017077  test    byte ptr [rcx+1Ch], 4
0x18001707b  jz      short loc_1800170A7
0x18001707d  mov     rcx, [rcx+10h]
0x180017081  lea     edx, [rdi+0Ah]
0x180017084  mov     [rbp+47h+var_50], r8
0x180017088  lea     r9, [rbp+47h+var_50]
0x18001708c  mov     dword ptr [rbp+47h+var_50+0Ch], esi
0x18001708f  lea     r8, WPP_e90ce2bd0edb3ab6daae4ad923eb703f_Traceguids
0x180017096  mov     dword ptr [rbp+47h+var_50+8], ebx
0x180017099  movaps  xmm0, xmmword ptr [rbp+47h+var_50]
0x18001709d  movdqa  xmmword ptr [rbp+47h+var_50], xmm0
0x1800170a2  call    WPP_SF__HEX_
0x1800170a7  cmp     [rbp+47h+arg_20], rsi
0x1800170ab  jz      loc_180017263
0x1800170b1  test    r14, r14
0x1800170b4  jz      loc_180017263
0x1800170ba  test    r15, r15
0x1800170bd  jz      loc_180017263
0x1800170c3  mov     r13d, [rbp+47h+arg_28]
0x1800170c7  test    r13d, r13d
0x1800170ca  jz      loc_180017263
0x1800170d0  mov     rcx, r15; pSid
0x1800170d3  call    cs:__imp_IsValidSid
0x1800170d9  test    eax, eax
0x1800170db  jnz     short loc_180017105
0x1800170dd  mov     r9d, 189h; unsigned int
0x1800170e3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800170ea  mov     ecx, 80070057h; unsigned int
0x1800170ef  lea     rdx, aHr; "hr"
0x1800170f6  mov     ebx, 80070057h
0x1800170fb  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017100  jmp     loc_1800172AB
0x180017105  mov     rcx, r14; pSecurityDescriptor
0x180017108  call    cs:__imp_IsValidSecurityDescriptor
0x18001710e  test    eax, eax
0x180017110  jnz     short loc_18001711A
0x180017112  mov     r9d, 191h
0x180017118  jmp     short loc_1800170E3
0x18001711a  mov     rcx, r14; pSecurityDescriptor
0x18001711d  call    cs:__imp_GetSecurityDescriptorLength
0x180017123  mov     r8d, 5
0x180017129  mov     rcx, r14
0x18001712c  mov     edx, eax
0x18001712e  mov     esi, eax
0x180017130  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x180017136  test    eax, eax
0x180017138  jnz     short loc_180017142
0x18001713a  mov     r9d, 19Eh
0x180017140  jmp     short loc_1800170E3
0x180017142  lea     r8, [rbp+47h+var_60]; struct _KEK_KEY_INFO **
0x180017146  mov     edx, ebx; unsigned int
0x180017148  mov     rcx, r12; unsigned __int8 *
0x18001714b  call    ?ValidateClientKEKInfo@@YAJQEAEKPEAPEAU_KEK_KEY_INFO@@@Z; ValidateClientKEKInfo(uchar * const,ulong,_KEK_KEY_INFO * *)
0x180017150  xor     r12d, r12d
0x180017153  mov     ebx, eax
0x180017155  test    eax, eax
0x180017157  js      loc_1800172AB
0x18001715d  mov     rdi, [rbp+47h+var_60]
0x180017161  mov     ecx, [rdi+28h]
0x180017164  lea     r9, [rdi+34h]
0x180017168  add     r9, rcx
0x18001716b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001716f  inc     rdx
0x180017172  cmp     [r9+rdx*2], r12w
0x180017177  jnz     short loc_18001716F
0x180017179  mov     eax, [rdi+2Ch]
0x18001717c  lea     r8, [rdi+18h]; struct _GUID *
0x180017180  add     rcx, 34h ; '4'
0x180017184  add     rcx, rax
0x180017187  lea     eax, ds:2[rdx*2]
0x18001718e  add     rcx, rdi
0x180017191  lea     rdx, [rbp+47h+var_70]
0x180017195  mov     [rsp+0E0h+var_80], rdx; unsigned int *
0x18001719a  lea     rdx, [rbp+47h+lpMem]
0x18001719e  mov     [rsp+0E0h+var_88], rdx; unsigned __int8 **
0x1800171a3  mov     edx, esi; unsigned int
0x1800171a5  mov     [rsp+0E0h+var_90], rcx; unsigned __int16 *
0x1800171aa  mov     rcx, r14; unsigned __int8 *
0x1800171ad  mov     [rsp+0E0h+var_98], eax; unsigned int
0x1800171b1  mov     eax, [rdi+14h]
0x1800171b4  mov     [rsp+0E0h+var_A0], r9; unsigned __int16 *
0x1800171b9  mov     r9d, [rdi+0Ch]; int
0x1800171bd  mov     dword ptr [rsp+0E0h+var_A8], r12d; unsigned int
0x1800171c2  mov     dword ptr [rsp+0E0h+var_B0], r12d; int
0x1800171c7  mov     dword ptr [rsp+0E0h+var_B8], eax; int
0x1800171cb  mov     eax, [rdi+10h]
0x1800171ce  mov     [rsp+0E0h+var_C0], eax; int
0x1800171d2  call    ?GetKeyFromKdsService@@YAJPEAEKPEAU_GUID@@JJJHKPEBGK2PEAPEAEPEAK@Z; GetKeyFromKdsService(uchar *,ulong,_GUID *,long,long,long,int,ulong,ushort const *,ulong,ushort const *,uchar * *,ulong *)
0x1800171d7  mov     ebx, eax
0x1800171d9  test    eax, eax
0x1800171db  jns     short loc_180017204
0x1800171dd  mov     r9d, 1C2h; unsigned int
0x1800171e3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800171ea  lea     rdx, aHr; "hr"
0x1800171f1  mov     ecx, eax; unsigned int
0x1800171f3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800171f8  mov     rdi, [rbp+47h+lpMem]
0x1800171fc  mov     esi, [rbp+47h+var_70]
0x1800171ff  jmp     loc_180017289
0x180017204  mov     rcx, r15; pSid
0x180017207  call    cs:__imp_GetLengthSid
0x18001720d  mov     rcx, [rbp+47h+arg_20]
0x180017211  mov     r8, rdi; struct _KEK_KEY_INFO *
0x180017214  mov     rdi, [rbp+47h+lpMem]
0x180017218  mov     r9, r15; unsigned __int8 *
0x18001721b  mov     esi, [rbp+47h+var_70]
0x18001721e  mov     edx, esi; unsigned int
0x180017220  mov     dword ptr [rsp+0E0h+var_A0], r13d; unsigned int
0x180017225  mov     [rsp+0E0h+var_A8], rcx; unsigned __int8 *
0x18001722a  mov     rcx, rdi; struct _SID_KEY_HEADER *
0x18001722d  mov     [rsp+0E0h+var_B0], r12; unsigned int *
0x180017232  mov     [rsp+0E0h+var_B8], r12; unsigned __int8 **
0x180017237  mov     [rsp+0E0h+var_C0], eax; DWORD
0x18001723b  call    ?_GenerateGmsaPassword@@YAJQEAEKPEAU_KEK_KEY_INFO@@PEAEKPEAPEAEPEAK2K@Z; _GenerateGmsaPassword(uchar * const,ulong,_KEK_KEY_INFO *,uchar *,ulong,uchar * *,ulong *,uchar *,ulong)
0x180017240  mov     ebx, eax
0x180017242  test    eax, eax
0x180017244  jns     short loc_180017289
0x180017246  mov     r9d, 1D3h; unsigned int
0x18001724c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017253  lea     rdx, aHr; "hr"
0x18001725a  mov     ecx, eax; unsigned int
0x18001725c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017261  jmp     short loc_180017289
0x180017263  mov     r9d, 182h; unsigned int
0x180017269  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017270  lea     rdx, aHr; "hr"
0x180017277  mov     ecx, 80070057h; unsigned int
0x18001727c  mov     ebx, 80070057h
0x180017281  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017286  xor     r12d, r12d
0x180017289  test    rdi, rdi
0x18001728c  jz      short loc_1800172AB
0x18001728e  mov     eax, esi
0x180017290  mov     rcx, rdi
0x180017293  test    esi, esi
0x180017295  jz      short loc_1800172A3
0x180017297  mov     [rcx], r12b
0x18001729a  inc     rcx
0x18001729d  sub     rax, 1
0x1800172a1  jnz     short loc_180017297
0x1800172a3  mov     rcx, rdi; lpMem
0x1800172a6  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800172ab  mov     eax, ebx
0x1800172ad  add     rsp, 0A8h
0x1800172b4  pop     r15
0x1800172b6  pop     r14
0x1800172b8  pop     r13
0x1800172ba  pop     r12
0x1800172bc  pop     rdi
0x1800172bd  pop     rsi
0x1800172be  pop     rbx
0x1800172bf  pop     rbp
0x1800172c0  retn
```

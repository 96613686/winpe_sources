# GetSpecifiedKey(_SECURITY_DESCRIPTOR *,ulong,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)

- ea: `0x180019bec`
- end: `0x18001a02b`
- name: `?GetSpecifiedKey@@YAJPEAU_SECURITY_DESCRIPTOR@@KKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z`
- size: `1087`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a034`

## callees

- `0x180003e08`
- `0x18000ce40`
- `0x180010624`
- `0x180010950`
- `0x180010980`
- `0x180017390`
- `0x1800187ec`
- `0x180018c7c`
- `0x180019274`
- `0x180019bec`
- `0x18001a450`

## string_xrefs

- `0x180019cd2`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019e80`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019f12`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019f5f`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GetSpecifiedKey(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8)
{
  int v8; // r12d
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // r9d
  int v16; // ebx
  unsigned int v17; // ecx
  int v18; // eax
  struct _KEK_KEY_INFO *v19; // rdi
  __int64 v20; // rsi
  unsigned __int16 *v21; // r13
  __int64 v22; // rbx
  int KeyInCache; // eax
  unsigned __int16 *v24; // r14
  unsigned __int16 *v25; // r15
  unsigned int v26; // ebx
  const unsigned __int16 *v27; // rsi
  unsigned __int8 *v28; // r13
  signed int KeyFromKdsService; // eax
  struct _SID_KEY_HEADER *v30; // rdi
  unsigned int v31; // esi
  struct _KEK_KEY_INFO *v32; // r8
  signed int SIDKey; // eax
  signed int v34; // eax
  __int64 v35; // rax
  struct _SID_KEY_HEADER *v36; // rcx
  unsigned __int16 *v38; // [rsp+48h] [rbp-69h]
  int v39; // [rsp+78h] [rbp-39h] BYREF
  int v40; // [rsp+7Ch] [rbp-35h] BYREF
  struct _KEK_KEY_INFO *v41; // [rsp+80h] [rbp-31h] BYREF
  struct _SID_KEY_HEADER *Src; // [rsp+88h] [rbp-29h] BYREF
  void *lpMem; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 *v44; // [rsp+98h] [rbp-19h] BYREF
  _QWORD v45[8]; // [rsp+A8h] [rbp-9h] BYREF

  v8 = 0;
  Src = 0;
  a8 = 0;
  lpMem = 0;
  v44 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
    {
      v14 = v13[2];
      v45[0] = a4;
      v45[1] = a5;
      WPP_SF__HEX_(v14, 13, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids, v45);
    }
  }
  if ( !a1 )
  {
    v15 = 1511;
LABEL_9:
    v16 = -2147024809;
    v17 = -2147024809;
LABEL_10:
    SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v15);
    goto LABEL_51;
  }
  if ( (a3 & 0xDFFFFFFF) != 0 )
  {
    v15 = 1518;
    goto LABEL_9;
  }
  v18 = IsLowbox(&v39);
  v16 = v18;
  if ( v18 < 0 )
  {
    v15 = 1525;
    v17 = v18;
    goto LABEL_10;
  }
  v16 = ValidateClientKEKInfo(a4, a5, &v41);
  if ( v16 < 0 )
    goto LABEL_51;
  v19 = v41;
  v20 = *((unsigned int *)v41 + 10);
  v21 = (unsigned __int16 *)((char *)v41 + v20 + 52);
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  LODWORD(v41) = *((_DWORD *)v41 + 11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
  KeyInCache = FindKeyInCache(v19, a1, a2, (unsigned int)v39, 0, 0, 0, &v40, &Src, &a8, &v44, &lpMem);
  v24 = (unsigned __int16 *)lpMem;
  v25 = v44;
  if ( KeyInCache >= 0 )
  {
    v8 = v40;
    if ( v40 )
    {
      v28 = a1;
LABEL_30:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
      v32 = v19;
      v30 = Src;
      v31 = a8;
      SIDKey = GenerateSIDKey(Src, a8, v32, a6, 0, 0, a7);
      v16 = SIDKey;
      if ( SIDKey >= 0 )
      {
        if ( !v8 )
        {
          if ( v24 )
          {
            if ( v25 )
            {
              v34 = WriteSIDKeyInCache(v30, v31, v28, a2, v25, v24);
              v16 = v34;
              if ( v34 < 0 )
              {
                SidKeyDebugTraceError(
                  v34,
                  "hr",
                  "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
                  0x658u);
                v16 = 0;
              }
            }
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
      }
      else
      {
        SidKeyDebugTraceError(
          SIDKey,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
          0x646u);
      }
      goto LABEL_43;
    }
    v8 = 0;
  }
  v26 = 2 * v22 + 2;
  v27 = (const unsigned __int16 *)((char *)v19 + (unsigned int)v41 + v20 + 52);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
  v38 = v21;
  v28 = a1;
  KeyFromKdsService = GetKeyFromKdsService(
                        a1,
                        a2,
                        (struct _GUID *)((char *)v19 + 24),
                        *((_DWORD *)v19 + 3),
                        *((_DWORD *)v19 + 4),
                        *((_DWORD *)v19 + 5),
                        v39,
                        a3,
                        v38,
                        v26,
                        v27,
                        (unsigned __int8 **)&Src,
                        &a8);
  v16 = KeyFromKdsService;
  if ( KeyFromKdsService >= 0 )
    goto LABEL_30;
  SidKeyDebugTraceError(
    KeyFromKdsService,
    "hr",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
    0x634u);
  v30 = Src;
  v31 = a8;
LABEL_43:
  if ( v24 )
    SIDKeyProvFree(v24);
  if ( v25 )
    SIDKeyProvFree(v25);
  if ( v30 )
  {
    v35 = v31;
    v36 = v30;
    if ( v31 )
    {
      do
      {
        *(_BYTE *)v36 = 0;
        v36 = (struct _SID_KEY_HEADER *)((char *)v36 + 1);
        --v35;
      }
      while ( v35 );
    }
    SIDKeyProvFree(v30);
  }
LABEL_51:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180019bec  mov     rax, rsp
0x180019bef  mov     [rax+20h], rbx
0x180019bf3  mov     [rax+18h], r8d
0x180019bf7  mov     [rax+10h], edx
0x180019bfa  mov     [rax+8], rcx
0x180019bfe  push    rbp
0x180019bff  push    rsi
0x180019c00  push    rdi
0x180019c01  push    r12
0x180019c03  push    r13
0x180019c05  push    r14
0x180019c07  push    r15
0x180019c09  lea     rbp, [rax-3Fh]
0x180019c0d  sub     rsp, 0B0h
0x180019c14  xor     r12d, r12d
0x180019c17  mov     rdi, r9
0x180019c1a  mov     [rbp+37h+Src], r12
0x180019c1e  mov     ebx, r8d
0x180019c21  mov     [rbp+37h+arg_38], r12d
0x180019c25  mov     r15d, edx
0x180019c28  mov     [rbp+37h+lpMem], r12
0x180019c2c  mov     r14, rcx
0x180019c2f  mov     [rbp+37h+var_50], r12
0x180019c33  mov     [rbp+37h+var_6C], r12d
0x180019c37  mov     [rbp+37h+var_68], r12
0x180019c3b  mov     [rbp+37h+var_70], r12d
0x180019c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c46  lea     rax, WPP_GLOBAL_Control
0x180019c4d  mov     esi, [rbp+37h+arg_20]
0x180019c50  cmp     rcx, rax
0x180019c53  jz      short loc_180019CB6
0x180019c55  test    byte ptr [rcx+1Ch], 4
0x180019c59  jz      short loc_180019C7E
0x180019c5b  mov     rcx, [rcx+10h]
0x180019c5f  lea     edx, [r12+0Ch]
0x180019c64  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019c6b  call    WPP_SF_
0x180019c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c77  lea     rax, WPP_GLOBAL_Control
0x180019c7e  cmp     rcx, rax
0x180019c81  jz      short loc_180019CB6
0x180019c83  test    byte ptr [rcx+1Ch], 4
0x180019c87  jz      short loc_180019CB6
0x180019c89  mov     rcx, [rcx+10h]
0x180019c8d  lea     r9, [rbp+37h+var_40]
0x180019c91  mov     dword ptr [rbp+37h+var_40+0Ch], r12d
0x180019c95  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019c9c  mov     [rbp+37h+var_40], rdi
0x180019ca0  mov     edx, 0Dh
0x180019ca5  mov     dword ptr [rbp+37h+var_40+8], esi
0x180019ca8  movaps  xmm0, xmmword ptr [rbp+37h+var_40]
0x180019cac  movdqa  xmmword ptr [rbp+37h+var_40], xmm0
0x180019cb1  call    WPP_SF__HEX_
0x180019cb6  test    r14, r14
0x180019cb9  jnz     short loc_180019CE3
0x180019cbb  mov     r9d, 5E7h; unsigned int
0x180019cc1  mov     ebx, 80070057h
0x180019cc6  mov     ecx, 80070057h; unsigned int
0x180019ccb  lea     rdx, aHr; "hr"
0x180019cd2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019cd9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019cde  jmp     loc_180019FE0
0x180019ce3  test    ebx, 0DFFFFFFFh
0x180019ce9  jz      short loc_180019CF3
0x180019ceb  mov     r9d, 5EEh
0x180019cf1  jmp     short loc_180019CC1
0x180019cf3  lea     rcx, [rbp+37h+var_70]; int *
0x180019cf7  call    ?IsLowbox@@YAJPEAH@Z; IsLowbox(int *)
0x180019cfc  mov     ebx, eax
0x180019cfe  test    eax, eax
0x180019d00  jns     short loc_180019D0C
0x180019d02  mov     r9d, 5F5h
0x180019d08  mov     ecx, eax
0x180019d0a  jmp     short loc_180019CCB
0x180019d0c  lea     r8, [rbp+37h+var_68]; struct _KEK_KEY_INFO **
0x180019d10  mov     edx, esi; unsigned int
0x180019d12  mov     rcx, rdi; unsigned __int8 *
0x180019d15  call    ?ValidateClientKEKInfo@@YAJQEAEKPEAPEAU_KEK_KEY_INFO@@@Z; ValidateClientKEKInfo(uchar * const,ulong,_KEK_KEY_INFO * *)
0x180019d1a  mov     ebx, eax
0x180019d1c  test    eax, eax
0x180019d1e  js      loc_180019FE0
0x180019d24  mov     rdi, [rbp+37h+var_68]
0x180019d28  mov     esi, [rdi+28h]
0x180019d2b  lea     r13, [rdi+34h]
0x180019d2f  add     r13, rsi
0x180019d32  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019d36  inc     rbx
0x180019d39  cmp     [r13+rbx*2+0], r12w
0x180019d3f  jnz     short loc_180019D36
0x180019d41  mov     eax, [rdi+2Ch]
0x180019d44  mov     dword ptr [rbp+37h+var_68], eax
0x180019d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d4e  lea     rax, WPP_GLOBAL_Control
0x180019d55  cmp     rcx, rax
0x180019d58  jz      short loc_180019D75
0x180019d5a  test    byte ptr [rcx+1Ch], 4
0x180019d5e  jz      short loc_180019D75
0x180019d60  mov     rcx, [rcx+10h]
0x180019d64  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019d6b  mov     edx, 0Eh
0x180019d70  call    WPP_SF_
0x180019d75  mov     r9d, [rbp+37h+var_70]
0x180019d79  lea     rax, [rbp+37h+lpMem]
0x180019d7d  mov     [rsp+0E0h+var_88], rax
0x180019d82  mov     r8d, r15d
0x180019d85  lea     rax, [rbp+37h+var_50]
0x180019d89  mov     rdx, r14
0x180019d8c  mov     [rsp+0E0h+var_90], rax
0x180019d91  mov     rcx, rdi
0x180019d94  lea     rax, [rbp+37h+arg_38]
0x180019d98  mov     qword ptr [rsp+0E0h+var_98], rax
0x180019d9d  lea     rax, [rbp+37h+Src]
0x180019da1  mov     [rsp+0E0h+var_A0], rax
0x180019da6  lea     rax, [rbp+37h+var_6C]
0x180019daa  mov     qword ptr [rsp+0E0h+var_A8], rax
0x180019daf  mov     [rsp+0E0h+var_B0], r12d
0x180019db4  mov     [rsp+0E0h+var_B8], r12
0x180019db9  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180019dbe  call    FindKeyInCache
0x180019dc3  mov     r14, [rbp+37h+lpMem]
0x180019dc7  mov     r15, [rbp+37h+var_50]
0x180019dcb  test    eax, eax
0x180019dcd  js      short loc_180019DDF
0x180019dcf  mov     r12d, [rbp+37h+var_6C]
0x180019dd3  test    r12d, r12d
0x180019dd6  jnz     loc_180019EA1
0x180019ddc  xor     r12d, r12d
0x180019ddf  mov     eax, dword ptr [rbp+37h+var_68]
0x180019de2  lea     ebx, ds:2[rbx*2]
0x180019de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019df0  add     rax, 34h ; '4'
0x180019df4  add     rsi, rax
0x180019df7  lea     rax, WPP_GLOBAL_Control
0x180019dfe  add     rsi, rdi
0x180019e01  cmp     rcx, rax
0x180019e04  jz      short loc_180019E21
0x180019e06  test    byte ptr [rcx+1Ch], 4
0x180019e0a  jz      short loc_180019E21
0x180019e0c  mov     rcx, [rcx+10h]
0x180019e10  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019e17  mov     edx, 0Fh
0x180019e1c  call    WPP_SF_
0x180019e21  mov     r9d, [rdi+0Ch]; int
0x180019e25  lea     rax, [rbp+37h+arg_38]
0x180019e29  mov     edx, [rbp+37h+arg_8]; unsigned int
0x180019e2c  lea     r8, [rdi+18h]; struct _GUID *
0x180019e30  mov     [rsp+60h], rax; unsigned int *
0x180019e35  lea     rax, [rbp+37h+Src]
0x180019e39  mov     [rsp+0E0h+var_88], rax; unsigned __int8 **
0x180019e3e  mov     eax, [rbp+37h+arg_10]
0x180019e41  mov     [rsp+0E0h+var_90], rsi; unsigned __int16 *
0x180019e46  mov     [rsp+0E0h+var_98], ebx; unsigned int
0x180019e4a  mov     [rsp+0E0h+var_A0], r13; unsigned __int16 *
0x180019e4f  mov     r13, [rbp+37h+arg_0]
0x180019e53  mov     [rsp+0E0h+var_A8], eax; unsigned int
0x180019e57  mov     rcx, r13; unsigned __int8 *
0x180019e5a  mov     eax, [rbp+37h+var_70]
0x180019e5d  mov     [rsp+0E0h+var_B0], eax; int
0x180019e61  mov     eax, [rdi+14h]
0x180019e64  mov     dword ptr [rsp+0E0h+var_B8], eax; int
0x180019e68  mov     eax, [rdi+10h]
0x180019e6b  mov     dword ptr [rsp+0E0h+var_C0], eax; int
0x180019e6f  call    ?GetKeyFromKdsService@@YAJPEAEKPEAU_GUID@@JJJHKPEBGK2PEAPEAEPEAK@Z; GetKeyFromKdsService(uchar *,ulong,_GUID *,long,long,long,int,ulong,ushort const *,ulong,ushort const *,uchar * *,ulong *)
0x180019e74  mov     ebx, eax
0x180019e76  test    eax, eax
0x180019e78  jns     short loc_180019EA5
0x180019e7a  mov     r9d, 634h; unsigned int
0x180019e80  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019e87  lea     rdx, aHr; "hr"
0x180019e8e  mov     ecx, eax; unsigned int
0x180019e90  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019e95  mov     rdi, [rbp+37h+Src]
0x180019e99  mov     esi, [rbp+37h+arg_38]
0x180019e9c  jmp     loc_180019FA4
0x180019ea1  mov     r13, [rbp+37h+arg_0]
0x180019ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019eac  lea     rax, WPP_GLOBAL_Control
0x180019eb3  cmp     rcx, rax
0x180019eb6  jz      short loc_180019ED3
0x180019eb8  test    byte ptr [rcx+1Ch], 4
0x180019ebc  jz      short loc_180019ED3
0x180019ebe  mov     rcx, [rcx+10h]
0x180019ec2  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019ec9  mov     edx, 10h
0x180019ece  call    WPP_SF_
0x180019ed3  mov     rax, [rbp+37h+arg_30]
0x180019ed7  mov     r8, rdi
0x180019eda  mov     rdi, [rbp+37h+Src]
0x180019ede  mov     esi, [rbp+37h+arg_38]
0x180019ee1  mov     rcx, rdi
0x180019ee4  mov     r9d, [rbp+37h+arg_28]
0x180019ee8  mov     edx, esi
0x180019eea  mov     qword ptr [rsp+0E0h+var_B0], rax
0x180019eef  mov     [rsp+0E0h+var_B8], 0
0x180019ef8  mov     [rsp+0E0h+var_C0], 0
0x180019f01  call    ?GenerateSIDKey@@YAJQEAEKPEAU_KEK_KEY_INFO@@W4_SID_KEY_BLOB_VER@@PEAPEAEPEAKPEAEK@Z; GenerateSIDKey(uchar * const,ulong,_KEK_KEY_INFO *,_SID_KEY_BLOB_VER,uchar * *,ulong *,uchar *,ulong)
0x180019f06  mov     ebx, eax
0x180019f08  test    eax, eax
0x180019f0a  jns     short loc_180019F29
0x180019f0c  mov     r9d, 646h; unsigned int
0x180019f12  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019f19  lea     rdx, aHr; "hr"
0x180019f20  mov     ecx, eax; unsigned int
0x180019f22  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019f27  jmp     short loc_180019FA4
0x180019f29  test    r12d, r12d
0x180019f2c  jnz     short loc_180019F76
0x180019f2e  test    r14, r14
0x180019f31  jz      short loc_180019F76
0x180019f33  test    r15, r15
0x180019f36  jz      short loc_180019F76
0x180019f38  mov     r9d, [rbp+37h+arg_8]; unsigned int
0x180019f3c  mov     r8, r13; unsigned __int8 *
0x180019f3f  mov     [rsp+0E0h+var_B8], r14; unsigned __int16 *
0x180019f44  mov     edx, esi; unsigned int
0x180019f46  mov     rcx, rdi; Src
0x180019f49  mov     [rsp+0E0h+var_C0], r15; unsigned __int16 *
0x180019f4e  call    ?WriteSIDKeyInCache@@YAJPEAU_SID_KEY_HEADER@@KPEAEKPEBG2@Z; WriteSIDKeyInCache(_SID_KEY_HEADER *,ulong,uchar *,ulong,ushort const *,ushort const *)
0x180019f53  mov     ebx, eax
0x180019f55  test    eax, eax
0x180019f57  jns     short loc_180019F76
0x180019f59  mov     r9d, 658h; unsigned int
0x180019f5f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019f66  lea     rdx, aHr; "hr"
0x180019f6d  mov     ecx, eax; unsigned int
0x180019f6f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019f74  xor     ebx, ebx
0x180019f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f7d  lea     rax, WPP_GLOBAL_Control
0x180019f84  cmp     rcx, rax
0x180019f87  jz      short loc_180019FA4
0x180019f89  test    byte ptr [rcx+1Ch], 4
0x180019f8d  jz      short loc_180019FA4
0x180019f8f  mov     rcx, [rcx+10h]
0x180019f93  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x180019f9a  mov     edx, 11h
0x180019f9f  call    WPP_SF_
0x180019fa4  test    r14, r14
0x180019fa7  jz      short loc_180019FB1
0x180019fa9  mov     rcx, r14; lpMem
0x180019fac  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019fb1  test    r15, r15
0x180019fb4  jz      short loc_180019FBE
0x180019fb6  mov     rcx, r15; lpMem
0x180019fb9  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019fbe  test    rdi, rdi
0x180019fc1  jz      short loc_180019FE0
0x180019fc3  mov     eax, esi
0x180019fc5  mov     rcx, rdi
0x180019fc8  test    esi, esi
0x180019fca  jz      short loc_180019FD8
0x180019fcc  mov     byte ptr [rcx], 0
0x180019fcf  inc     rcx
0x180019fd2  sub     rax, 1
0x180019fd6  jnz     short loc_180019FCC
0x180019fd8  mov     rcx, rdi; lpMem
0x180019fdb  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fe7  lea     rax, WPP_GLOBAL_Control
0x180019fee  cmp     rcx, rax
0x180019ff1  jz      short loc_18001A00E
0x180019ff3  test    byte ptr [rcx+1Ch], 4
0x180019ff7  jz      short loc_18001A00E
0x180019ff9  mov     rcx, [rcx+10h]
0x180019ffd  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x18001a004  mov     edx, 12h
0x18001a009  call    WPP_SF_
0x18001a00e  mov     eax, ebx
0x18001a010  mov     rbx, [rsp+0E0h+arg_18]
0x18001a018  add     rsp, 0B0h
0x18001a01f  pop     r15
0x18001a021  pop     r14
0x18001a023  pop     r13
0x18001a025  pop     r12
0x18001a027  pop     rdi
0x18001a028  pop     rsi
0x18001a029  pop     rbp
0x18001a02a  retn
```

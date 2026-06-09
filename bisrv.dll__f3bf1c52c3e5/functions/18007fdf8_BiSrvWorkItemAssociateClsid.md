# BiSrvWorkItemAssociateClsid

- ea: `0x18007fdf8`
- end: `0x180080286`
- name: `BiSrvWorkItemAssociateClsid`
- size: `1166`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800486fc`
- `0x180093420`

## callees

- `0x180002600`
- `0x1800075f8`
- `0x180008560`
- `0x180008598`
- `0x180009430`
- `0x1800095b0`
- `0x18000a430`
- `0x18000b9d0`
- `0x18001027c`
- `0x180037500`
- `0x18004df58`
- `0x180053100`
- `0x180057614`
- `0x1800793f8`
- `0x18007fdf8`
- `0x180094656`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180080213`
- `ntdll!RtlFreeHeap` at `0x18008021b`
- `ntdll!RtlFreeHeap` at `0x180080213`
- `ntdll!RtlFreeHeap` at `0x18008021b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180080247`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180080247`
- `ntdll!RtlEqualSid` at `0x18007fff6`
- `ntdll!RtlEqualSid` at `0x18007fff6`

## pseudocode

```c
__int64 __fastcall BiSrvWorkItemAssociateClsid(
        UUID *a1,
        __int64 *a2,
        __int64 a3,
        void *a4,
        unsigned int a5,
        unsigned int a6,
        struct _GUID *a7,
        GUID *Buf1,
        void *Source1,
        struct _BI_CONDITIONAL_EVENT_INFORMATION *a10,
        __int64 a11,
        unsigned int a12,
        struct _UNICODE_STRING *a13,
        __int64 a14,
        int a15,
        signed int *a16)
{
  signed int *v18; // r13
  __int64 Buffer; // r8
  __int64 v20; // rcx
  __int64 *v21; // r8
  __int64 v22; // r9
  unsigned int v23; // esi
  int v24; // ebx
  int v25; // eax
  __int64 v26; // r14
  signed int v27; // eax
  int v29; // [rsp+30h] [rbp-D0h]
  size_t v30; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  struct _BI_CONDITIONAL_EVENT_INFORMATION *v33; // [rsp+A0h] [rbp-60h]
  struct _GUID *v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 *v36; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v37; // [rsp+C0h] [rbp-40h] BYREF
  void *v38; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  PCUNICODE_STRING SourceString; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  int v44[2]; // [rsp+F8h] [rbp-8h]
  GUID Guid; // [rsp+100h] [rbp+0h] BYREF
  __int128 v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+120h] [rbp+20h]
  _BYTE v48[400]; // [rsp+130h] [rbp+30h] BYREF

  v18 = a16;
  v34 = a7;
  v33 = a10;
  v42 = a11;
  v40 = a3;
  v43 = (__int64)a2;
  v32 = 0;
  v39 = a14;
  SourceString = a13;
  *(_QWORD *)v44 = Source1;
  memset_0(v48, 0, 0x182u);
  v35 = 0;
  v47 = 0;
  Buffer = 0;
  v46 = 0;
  Guid = *Buf1;
  if ( a13 && a13->Length )
  {
    Buffer = (__int64)a13->Buffer;
    v35 = Buffer;
  }
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, Buffer) )
  {
    v36 = v21;
    v37 = a2;
    v38 = Source1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v20,
      (__int64)byte_1800B4175,
      (__int64)v21,
      v22,
      (__int64 *)&v38,
      &v37,
      &v36);
  }
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v23 = a6;
    v24 = -1073741811;
    v25 = 10;
    goto LABEL_50;
  }
  if ( (a5 & 1) == 0 )
    BipStorageSynchronizeWithInitialization();
  v24 = BipLookupEventByGuid(Source1);
  if ( v24 >= 0 )
  {
    if ( MEMORY[0xA8] )
    {
      if ( MEMORY[0xC0] )
      {
        v24 = BipPackageIdFromOptionalFullName(&v32, v48, a2);
        if ( v24 >= 0 )
        {
          if ( !a4 || MEMORY[0xA8] && RtlEqualSid(a4, MEMORY[0xA8]) )
          {
            v26 = v32;
            v24 = 0;
            if ( v32
              && !(unsigned __int8)BipPackageIdIsEquivalent(v32, 192)
              && (v24 = -1073741823, (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0)
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
            }
            else if ( v24 >= 0 )
            {
              if ( !v26 )
                v26 = 192;
              if ( !a4 )
                a4 = (void *)MEMORY[0xA8];
              v23 = a6;
              if ( (a5 & 2) != 0 )
              {
                if ( (MEMORY[0x18] & 2) != 0 )
                  v23 = a6 | 2;
                else
                  v23 = a6 & 0xFFFFFFFD;
              }
              v24 = BipValidateAssociateParameters(a1, a5, v23, v34, 0, v33, a12, a13);
              if ( v24 >= 0 )
              {
                if ( (a5 & 1) == 0 )
                {
                  BipPackageCheckUpdateStaleFullName(v26, a4);
                  BipPackageEnsureIsRegistered(0xFFFFFFFF, a4, (const WCHAR *)(v26 + 256));
                }
                v23 &= ~0x20u;
                LODWORD(v30) = a15;
                v24 = BipWorkItemCreate(
                        a1,
                        a5,
                        v23,
                        v34,
                        2u,
                        (__int128 *)&Guid,
                        0,
                        (__int64)v33,
                        (unsigned int *)v42,
                        a12,
                        SourceString,
                        v40,
                        0,
                        (void *)v39,
                        v30);
                if ( v24 >= 0 )
                {
                  v24 = 0;
                  v25 = 0;
                }
                else
                {
                  v25 = 80;
                }
              }
              else
              {
                v25 = 70;
              }
              goto LABEL_49;
            }
          }
          else
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
            v24 = -1073741823;
          }
          v25 = 60;
        }
        else
        {
          v25 = 50;
        }
      }
      else
      {
        v24 = -1073741811;
        v25 = 40;
      }
    }
    else
    {
      v24 = -1073741811;
      v25 = 30;
    }
  }
  else
  {
    v25 = 20;
  }
  v23 = a6;
LABEL_49:
  v18 = a16;
LABEL_50:
  BipTraceWorkItemAssociateStop(v44[0], (int)a1, a5, v23, v35, v43, v29, &Guid, v24, v25);
  if ( v18 )
  {
    if ( v24 >= 0 )
    {
      v27 = 0;
    }
    else
    {
      v27 = RtlNtStatusToDosErrorNoTeb(v24);
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
    }
    *v18 = v27;
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18007fdf8  push    rbp
0x18007fdfa  push    rbx
0x18007fdfb  push    rsi
0x18007fdfc  push    rdi
0x18007fdfd  push    r12
0x18007fdff  push    r13
0x18007fe01  push    r14
0x18007fe03  push    r15
0x18007fe05  lea     rbp, [rsp-1D8h]
0x18007fe0d  sub     rsp, 2D8h
0x18007fe14  mov     rax, cs:__security_cookie
0x18007fe1b  xor     rax, rsp
0x18007fe1e  mov     [rbp+210h+var_50], rax
0x18007fe25  mov     rax, [rbp+210h+arg_30]
0x18007fe2c  mov     r14, rdx
0x18007fe2f  mov     r15, [rbp+210h+arg_60]
0x18007fe36  mov     r12, r9
0x18007fe39  mov     rsi, [rbp+210h+Source1]
0x18007fe40  mov     r13, [rbp+210h+arg_78]
0x18007fe47  mov     rbx, [rbp+210h+Buf1]
0x18007fe4e  mov     [rbp+210h+var_268], rax
0x18007fe52  mov     rax, [rbp+210h+arg_48]
0x18007fe59  mov     [rbp+210h+var_270], rax
0x18007fe5d  mov     rax, [rbp+210h+arg_50]
0x18007fe64  mov     [rbp+210h+var_280], rcx
0x18007fe68  xor     ecx, ecx
0x18007fe6a  mov     [rbp+210h+var_228], rax
0x18007fe6e  mov     rax, [rbp+210h+arg_68]
0x18007fe75  mov     [rbp+210h+var_238], r8
0x18007fe79  mov     r8d, 182h; Size
0x18007fe7f  mov     [rbp+210h+var_220], rdx
0x18007fe83  xor     edx, edx; Val
0x18007fe85  mov     [rbp+210h+var_278], rcx
0x18007fe89  lea     rcx, [rbp+210h+var_1E0]; void *
0x18007fe8d  mov     [rbp+210h+var_240], rax
0x18007fe91  mov     [rbp+210h+var_230], r15
0x18007fe95  mov     qword ptr [rbp+210h+var_218], rsi
0x18007fe99  mov     [rbp+210h+var_290], r13
0x18007fe9d  call    memset_0
0x18007fea2  xor     r9d, r9d
0x18007fea5  xorps   xmm0, xmm0
0x18007fea8  xor     eax, eax
0x18007feaa  mov     [rbp+210h+var_288], r9
0x18007feae  mov     [rbp+210h+var_260], r9
0x18007feb2  mov     edi, r9d
0x18007feb5  mov     [rbp+210h+var_1F0], rax
0x18007feb9  mov     r8d, r9d
0x18007febc  movups  [rbp+210h+var_200], xmm0
0x18007fec0  movups  xmm0, xmmword ptr [rbx]
0x18007fec3  movdqu  xmmword ptr [rbp+210h+var_210.Data1], xmm0
0x18007fec8  test    r15, r15
0x18007fecb  jz      short loc_18007FEDB
0x18007fecd  cmp     [r15], r9w
0x18007fed1  jbe     short loc_18007FEDB
0x18007fed3  mov     r8, [r15+8]
0x18007fed7  mov     [rbp+210h+var_260], r8
0x18007fedb  mov     eax, cs:dword_1800C3098
0x18007fee1  cmp     eax, 4
0x18007fee4  jbe     short loc_18007FF2E
0x18007fee6  mov     edx, 3
0x18007feeb  lea     rcx, dword_1800C3098
0x18007fef2  call    _tlgKeywordOn
0x18007fef7  test    al, al
0x18007fef9  jz      short loc_18007FF2E
0x18007fefb  lea     rax, [rbp+210h+var_258]
0x18007feff  mov     [rbp+210h+var_258], r8
0x18007ff03  mov     qword ptr [rsp+310h+var_2E0], rax
0x18007ff08  lea     rdx, byte_1800B4175
0x18007ff0f  lea     rax, [rbp+210h+var_250]
0x18007ff13  mov     [rbp+210h+var_250], r14
0x18007ff17  mov     [rsp+310h+var_2E8], rax
0x18007ff1c  lea     rax, [rbp+210h+var_248]
0x18007ff20  mov     [rsp+310h+var_2F0], rax
0x18007ff25  mov     [rbp+210h+var_248], rsi
0x18007ff29  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18007ff2e  mov     r8d, 10h; Size
0x18007ff34  lea     rdx, GUID_NULL; Buf2
0x18007ff3b  mov     rcx, rbx; Buf1
0x18007ff3e  call    memcmp_0
0x18007ff43  test    eax, eax
0x18007ff45  jnz     short loc_18007FF5C
0x18007ff47  mov     esi, [rbp+210h+arg_28]
0x18007ff4d  mov     ebx, 0C000000Dh
0x18007ff52  mov     eax, 0Ah
0x18007ff57  jmp     loc_1800801AA
0x18007ff5c  mov     r13d, [rbp+210h+arg_20]
0x18007ff63  and     r13d, 1
0x18007ff67  jnz     short loc_18007FF6E
0x18007ff69  call    BipStorageSynchronizeWithInitialization
0x18007ff6e  lea     rdx, [rbp+210h+var_288]
0x18007ff72  mov     rcx, rsi; Source1
0x18007ff75  call    BipLookupEventByGuid
0x18007ff7a  mov     rdi, [rbp+210h+var_288]
0x18007ff7e  mov     ebx, eax
0x18007ff80  xor     eax, eax
0x18007ff82  test    ebx, ebx
0x18007ff84  jns     short loc_18007FF96
0x18007ff86  mov     eax, 14h
0x18007ff8b  mov     esi, [rbp+210h+arg_28]
0x18007ff91  jmp     loc_1800801A6
0x18007ff96  cmp     [rdi+0A8h], rax
0x18007ff9d  jnz     short loc_18007FFAB
0x18007ff9f  mov     ebx, 0C000000Dh
0x18007ffa4  mov     eax, 1Eh
0x18007ffa9  jmp     short loc_18007FF8B
0x18007ffab  lea     rsi, [rdi+0C0h]
0x18007ffb2  cmp     [rsi], ax
0x18007ffb5  jnz     short loc_18007FFC3
0x18007ffb7  mov     ebx, 0C000000Dh
0x18007ffbc  mov     eax, 28h ; '('
0x18007ffc1  jmp     short loc_18007FF8B
0x18007ffc3  mov     r8, r14
0x18007ffc6  lea     rdx, [rbp+210h+var_1E0]
0x18007ffca  lea     rcx, [rbp+210h+var_278]
0x18007ffce  call    BipPackageIdFromOptionalFullName
0x18007ffd3  xor     r8d, r8d
0x18007ffd6  mov     ebx, eax
0x18007ffd8  test    eax, eax
0x18007ffda  jns     short loc_18007FFE2
0x18007ffdc  lea     eax, [r8+32h]
0x18007ffe0  jmp     short loc_18007FF8B
0x18007ffe2  test    r12, r12
0x18007ffe5  jz      short loc_180080032
0x18007ffe7  mov     rdx, [rdi+0A8h]; Sid2
0x18007ffee  test    rdx, rdx
0x18007fff1  jz      short loc_180080003
0x18007fff3  mov     rcx, r12; Sid1
0x18007fff6  call    cs:__imp_RtlEqualSid
0x18007fffc  xor     r8d, r8d
0x18007ffff  test    al, al
0x180080001  jnz     short loc_180080032
0x180080003  mov     rcx, cs:WPP_GLOBAL_Control
0x18008000a  test    byte ptr [rcx+1Ch], 40h
0x18008000e  jz      short loc_18008002B
0x180080010  cmp     byte ptr [rcx+19h], 2
0x180080014  jb      short loc_18008002B
0x180080016  mov     rcx, [rcx+10h]
0x18008001a  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x180080021  mov     edx, 0Ah
0x180080026  call    WPP_SF_
0x18008002b  mov     ebx, 0C0000001h
0x180080030  jmp     short loc_180080080
0x180080032  mov     r14, [rbp+210h+var_278]
0x180080036  mov     ebx, r8d
0x180080039  test    r14, r14
0x18008003c  jz      short loc_18008007C
0x18008003e  mov     rdx, rsi
0x180080041  mov     rcx, r14
0x180080044  call    BipPackageIdIsEquivalent
0x180080049  test    al, al
0x18008004b  jnz     short loc_18008007C
0x18008004d  mov     ebx, 0C0000001h
0x180080052  mov     rcx, cs:WPP_GLOBAL_Control
0x180080059  test    byte ptr [rcx+1Ch], 40h
0x18008005d  jz      short loc_18008007C
0x18008005f  cmp     byte ptr [rcx+19h], 2
0x180080063  jb      short loc_18008007C
0x180080065  mov     rcx, [rcx+10h]
0x180080069  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x180080070  mov     edx, 0Bh
0x180080075  call    WPP_SF_
0x18008007a  jmp     short loc_180080080
0x18008007c  test    ebx, ebx
0x18008007e  jns     short loc_18008008A
0x180080080  mov     eax, 3Ch ; '<'
0x180080085  jmp     loc_18007FF8B
0x18008008a  test    r14, r14
0x18008008d  cmovz   r14, rsi
0x180080091  test    r12, r12
0x180080094  jnz     short loc_18008009D
0x180080096  mov     r12, [rdi+0A8h]
0x18008009d  test    byte ptr [rbp+210h+arg_20], 2
0x1800800a4  mov     esi, [rbp+210h+arg_28]
0x1800800aa  jz      short loc_1800800BA
0x1800800ac  test    byte ptr [rdi+18h], 2
0x1800800b0  jz      short loc_1800800B7
0x1800800b2  or      esi, 2
0x1800800b5  jmp     short loc_1800800BA
0x1800800b7  and     esi, 0FFFFFFFDh
0x1800800ba  mov     rax, [rbp+210h+var_270]
0x1800800be  mov     r8d, esi; unsigned int
0x1800800c1  mov     r9, [rbp+210h+var_268]; struct _GUID *
0x1800800c5  mov     edx, [rbp+210h+arg_20]; unsigned int
0x1800800cb  mov     rcx, [rbp+210h+var_280]; struct _GUID *
0x1800800cf  mov     [rsp+310h+Guid], r15; struct _UNICODE_STRING *
0x1800800d4  mov     r15d, [rbp+210h+arg_58]
0x1800800db  mov     [rsp+310h+var_2E0], r15d; unsigned int
0x1800800e0  mov     [rsp+310h+var_2E8], rax; struct _BI_CONDITIONAL_EVENT_INFORMATION *
0x1800800e5  mov     [rsp+310h+var_2F0], rdi; struct _BI_EVENT *
0x1800800ea  call    ?BipValidateAssociateParameters@@YAJPEAU_GUID@@KKPEBU1@PEAU_BI_EVENT@@PEAU_BI_CONDITIONAL_EVENT_INFORMATION@@KPEAU_UNICODE_STRING@@@Z; BipValidateAssociateParameters(_GUID *,ulong,ulong,_GUID const *,_BI_EVENT *,_BI_CONDITIONAL_EVENT_INFORMATION *,ulong,_UNICODE_STRING *)
0x1800800ef  mov     ebx, eax
0x1800800f1  test    eax, eax
0x1800800f3  jns     short loc_1800800FF
0x1800800f5  mov     eax, 46h ; 'F'
0x1800800fa  jmp     loc_1800801A6
0x1800800ff  test    r13d, r13d
0x180080102  jnz     short loc_180080121
0x180080104  mov     rdx, r12
0x180080107  mov     rcx, r14
0x18008010a  call    BipPackageCheckUpdateStaleFullName
0x18008010f  lea     r8, [r14+100h]
0x180080116  mov     rdx, r12; Sid1
0x180080119  or      ecx, 0FFFFFFFFh; SessionId
0x18008011c  call    BipPackageEnsureIsRegistered
0x180080121  mov     eax, dword ptr [rbp+210h+arg_70]
0x180080127  xor     r14d, r14d
0x18008012a  mov     r9, [rbp+210h+var_268]; int
0x18008012e  and     esi, 0FFFFFFDFh
0x180080131  mov     edx, [rbp+210h+arg_20]; int
0x180080137  mov     r8d, esi; int
0x18008013a  mov     rcx, [rbp+210h+var_280]; int
0x18008013e  mov     dword ptr [rsp+310h+var_2A0], eax; size_t
0x180080142  mov     rax, [rbp+210h+var_240]
0x180080146  mov     [rsp+310h+var_2A8], rax; __int64
0x18008014b  mov     rax, [rbp+210h+var_238]
0x18008014f  mov     dword ptr [rsp+310h+var_2B0], r14d; char
0x180080154  mov     [rsp+310h+var_2B8], rax; __int64
0x180080159  mov     rax, [rbp+210h+var_230]
0x18008015d  mov     [rsp+310h+SourceString], rax; SourceString
0x180080162  mov     rax, [rbp+210h+var_228]
0x180080166  mov     [rsp+310h+var_2C8], r15d; int
0x18008016b  mov     [rsp+310h+var_2D0], rax; __int64
0x180080170  mov     rax, [rbp+210h+var_270]
0x180080174  mov     [rsp+310h+Guid], rax; __int64
0x180080179  lea     rax, [rbp+210h+var_210]
0x18008017d  mov     qword ptr [rsp+310h+var_2E0], rdi; int
0x180080182  mov     [rsp+310h+var_2E8], rax; __int64
0x180080187  mov     dword ptr [rsp+310h+var_2F0], 2; int
0x18008018f  call    BipWorkItemCreate
0x180080194  mov     ebx, eax
0x180080196  test    eax, eax
0x180080198  jns     short loc_1800801A0
0x18008019a  lea     eax, [r14+50h]
0x18008019e  jmp     short loc_1800801A6
0x1800801a0  mov     ebx, r14d
0x1800801a3  mov     eax, r14d
0x1800801a6  mov     r13, [rbp+210h+var_290]
0x1800801aa  mov     r8d, [rbp+210h+arg_20]; int
0x1800801b1  mov     r9d, esi; int
0x1800801b4  mov     rdx, [rbp+210h+var_280]; int
0x1800801b8  mov     rcx, qword ptr [rbp+210h+var_218]; int
0x1800801bc  mov     [rsp+310h+var_2C8], eax; int
0x1800801c0  lea     rax, [rbp+210h+var_210]
0x1800801c4  mov     dword ptr [rsp+310h+var_2D0], ebx; int
0x1800801c8  mov     [rsp+310h+Guid], rax; Guid
0x1800801cd  mov     rax, [rbp+210h+var_220]
0x1800801d1  mov     [rsp+310h+var_2E8], rax; __int64
0x1800801d6  mov     rax, [rbp+210h+var_260]
0x1800801da  mov     [rsp+310h+var_2F0], rax; __int64
0x1800801df  call    BipTraceWorkItemAssociateStop
0x1800801e4  xor     esi, esi
0x1800801e6  test    rdi, rdi
0x1800801e9  jz      short loc_18008023C
0x1800801eb  or      eax, 0FFFFFFFFh
0x1800801ee  lock xadd [rdi+1Ch], eax
0x1800801f3  cmp     eax, 1
0x1800801f6  jnz     short loc_18008023C
0x1800801f8  mov     ecx, [rdi+30h]
0x1800801fb  sub     ecx, eax
0x1800801fd  jz      short loc_18008022D
0x1800801ff  sub     ecx, eax
0x180080201  jz      short loc_180080223
0x180080203  xor     edx, edx; Flags
0x180080205  mov     r8, rdi; P
0x180080208  cmp     ecx, eax
0x18008020a  mov     rcx, cs:BipHeap; HeapHandle
0x180080211  jz      short loc_18008021B
0x180080213  call    cs:__imp_RtlFreeHeap
0x180080219  jmp     short loc_18008023C
0x18008021b  call    cs:__imp_RtlFreeHeap
0x180080221  jmp     short loc_18008023C
0x180080223  mov     rcx, rdi; struct _BI_WORK_ITEM *
0x180080226  call    BipWorkItemCheckQueueDestroy
0x18008022b  jmp     short loc_18008023C
0x18008022d  mov     rdx, rdi
0x180080230  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x180080237  call    BipEventQueueDestroy
0x18008023c  test    r13, r13
0x18008023f  jz      short loc_180080261
0x180080241  test    ebx, ebx
0x180080243  jns     short loc_18008025B
0x180080245  mov     ecx, ebx; Status
0x180080247  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18008024d  test    eax, eax
0x18008024f  jle     short loc_18008025D
0x180080251  movzx   eax, ax
0x180080254  or      eax, 80070000h
0x180080259  jmp     short loc_18008025D
0x18008025b  mov     eax, esi
0x18008025d  mov     [r13+0], eax
0x180080261  mov     eax, ebx
0x180080263  mov     rcx, [rbp+210h+var_50]
0x18008026a  xor     rcx, rsp; StackCookie
0x18008026d  call    __security_check_cookie
0x180080272  add     rsp, 2D8h
0x180080279  pop     r15
0x18008027b  pop     r14
0x18008027d  pop     r13
0x18008027f  pop     r12
0x180080281  pop     rdi
  ... truncated ...
```

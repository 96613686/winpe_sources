# FindKeyForOfflineUsage(int,ushort const *,ushort const *,ulong,int *,_SID_KEY_HEADER * *,ulong *)

- ea: `0x18000b310`
- end: `0x18000b58d`
- name: `?FindKeyForOfflineUsage@@YAJHPEBG0KPEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z`
- size: `637`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, int *, struct _SID_KEY_HEADER **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800196cc`

## callees

- `0x18000aef0`
- `0x18000b310`
- `0x1800100d0`
- `0x18001a450`

## string_xrefs

- `0x18000b55e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall FindKeyForOfflineUsage(
        int a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        int *a5,
        struct _SID_KEY_HEADER **a6,
        unsigned int *a7)
{
  unsigned int v7; // ebx
  unsigned __int64 v9; // rdi
  unsigned __int64 CurrentTimeInULL; // rax
  unsigned __int64 v11; // rax
  unsigned int v12; // ebp
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rsi
  int v15; // ebx
  const unsigned __int16 *v16; // rbp
  signed int SIDKeyInCache; // eax
  unsigned int v18; // r9d
  unsigned int v20[2]; // [rsp+60h] [rbp-48h]
  int v21; // [rsp+60h] [rbp-48h]
  __int64 v22; // [rsp+68h] [rbp-40h]

  v7 = a4;
  v9 = GetCurrentTimeInULL() / 0x14F46B0400000LL;
  CurrentTimeInULL = GetCurrentTimeInULL();
  if ( CurrentTimeInULL < 0x7DBA8218000LL )
    v11 = -1;
  else
    v11 = CurrentTimeInULL - 8640000000000LL;
  v12 = v9;
  v13 = v11 / 0x53D1AC1000LL;
  *(_QWORD *)v20 = v13;
  v14 = v13 >> 10;
  if ( (unsigned int)(v13 >> 10) >= (unsigned int)v9 )
  {
LABEL_9:
    v16 = a3;
    v22 = (v13 >> 5) & 0x1F;
    v21 = v13 & 0x1F;
    SIDKeyInCache = FindAndReadSIDKeyInCache(0, v14, (v13 >> 5) & 0x1F, v21, a1, 1, a3, v7, a2, a5, a6, a7);
    v15 = SIDKeyInCache;
    if ( SIDKeyInCache >= 0 )
    {
      if ( (unsigned int)v14 < (unsigned int)v9 )
      {
        while ( 1 )
        {
          v15 = FindAndReadSIDKeyInCache(0, v9, 0, 0, a1 == 0, 1, a3, a4, a2, a5, a6, a7);
          if ( v15 >= 0 )
          {
            if ( *a5 )
              return (unsigned int)v15;
          }
          LODWORD(v9) = v9 - 1;
          if ( (unsigned int)v14 >= (unsigned int)v9 )
          {
            v16 = a3;
            break;
          }
        }
      }
      SIDKeyInCache = FindAndReadSIDKeyInCache(0, v14, v22, v21, a1 == 0, 1, v16, a4, a2, a5, a6, a7);
      v15 = SIDKeyInCache;
      if ( SIDKeyInCache >= 0 )
        return (unsigned int)v15;
      v18 = 1564;
    }
    else
    {
      v18 = 1508;
    }
    SidKeyDebugTraceError(
      SIDKeyInCache,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      v18);
    return (unsigned int)v15;
  }
  while ( 1 )
  {
    v15 = FindAndReadSIDKeyInCache(0, v12, 0, 0, a1, 1, a3, v7, a2, a5, a6, a7);
    if ( v15 >= 0 )
    {
      if ( *a5 )
        return (unsigned int)v15;
    }
    v7 = a4;
    if ( (unsigned int)v14 >= --v12 )
    {
      v13 = *(_QWORD *)v20;
      goto LABEL_9;
    }
  }
}

```

## disassembly

```asm
0x18000b310  mov     rax, rsp
0x18000b313  mov     [rax+8], rbx
0x18000b317  mov     [rax+20h], r9d
0x18000b31b  mov     [rax+18h], r8
0x18000b31f  mov     [rax+10h], rdx
0x18000b323  push    rbp
0x18000b324  push    rsi
0x18000b325  push    rdi
0x18000b326  push    r12
0x18000b328  push    r13
0x18000b32a  push    r14
0x18000b32c  push    r15
0x18000b32e  sub     rsp, 70h
0x18000b332  mov     ebx, r9d
0x18000b335  mov     r13d, ecx
0x18000b338  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000b33d  xor     edx, edx
0x18000b33f  mov     rsi, 53D1AC1000h
0x18000b349  div     rsi
0x18000b34c  mov     rdi, rax
0x18000b34f  shr     rdi, 0Ah
0x18000b353  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000b358  mov     rcx, 7DBA8218000h
0x18000b362  cmp     rax, rcx
0x18000b365  jb      short loc_18000B376
0x18000b367  mov     rcx, 0FFFFF82457DE8000h
0x18000b371  add     rax, rcx
0x18000b374  jmp     short loc_18000B37A
0x18000b376  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b37a  mov     r15, [rsp+0A8h+arg_30]
0x18000b382  xor     edx, edx
0x18000b384  mov     r12, [rsp+0A8h+arg_28]
0x18000b38c  mov     ebp, edi
0x18000b38e  mov     r14, [rsp+0A8h+arg_20]
0x18000b396  div     rsi
0x18000b399  mov     rsi, rax
0x18000b39c  mov     qword ptr [rsp+0A8h+var_48], rax
0x18000b3a1  shr     rsi, 0Ah
0x18000b3a5  cmp     esi, edi
0x18000b3a7  jnb     short loc_18000B414
0x18000b3a9  mov     rax, [rsp+0A8h+arg_8]
0x18000b3b1  xor     r9d, r9d; unsigned int
0x18000b3b4  mov     [rsp+0A8h+var_50], r15; unsigned int *
0x18000b3b9  xor     r8d, r8d; unsigned int
0x18000b3bc  mov     [rsp+0A8h+var_58], r12; struct _SID_KEY_HEADER **
0x18000b3c1  mov     edx, ebp; unsigned int
0x18000b3c3  mov     [rsp+0A8h+var_60], r14; int *
0x18000b3c8  xor     ecx, ecx; struct _GUID *
0x18000b3ca  mov     [rsp+0A8h+var_68], rax; unsigned __int16 *
0x18000b3cf  mov     rax, [rsp+0A8h+arg_10]
0x18000b3d7  mov     [rsp+0A8h+var_70], ebx; unsigned int
0x18000b3db  mov     [rsp+0A8h+var_78], rax; unsigned __int16 *
0x18000b3e0  mov     [rsp+0A8h+var_80], 1; int
0x18000b3e8  mov     [rsp+0A8h+var_88], r13d; int
0x18000b3ed  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x18000b3f2  mov     ebx, eax
0x18000b3f4  test    eax, eax
0x18000b3f6  js      short loc_18000B402
0x18000b3f8  cmp     dword ptr [r14], 0
0x18000b3fc  jnz     loc_18000B573
0x18000b402  mov     ebx, [rsp+0A8h+arg_18]
0x18000b409  dec     ebp
0x18000b40b  cmp     esi, ebp
0x18000b40d  jb      short loc_18000B3A9
0x18000b40f  mov     rax, qword ptr [rsp+0A8h+var_48]
0x18000b414  mov     rdx, [rsp+0A8h+arg_8]
0x18000b41c  mov     rcx, rax
0x18000b41f  mov     rbp, [rsp+0A8h+arg_10]
0x18000b427  and     eax, 1Fh
0x18000b42a  mov     [rsp+0A8h+var_50], r15; unsigned int *
0x18000b42f  mov     r9d, eax; unsigned int
0x18000b432  mov     [rsp+0A8h+var_58], r12; struct _SID_KEY_HEADER **
0x18000b437  mov     [rsp+0A8h+var_60], r14; int *
0x18000b43c  mov     [rsp+0A8h+var_68], rdx; unsigned __int16 *
0x18000b441  mov     edx, esi; unsigned int
0x18000b443  shr     rcx, 5
0x18000b447  and     ecx, 1Fh
0x18000b44a  mov     [rsp+0A8h+var_70], ebx; unsigned int
0x18000b44e  mov     qword ptr [rsp+0A8h+var_40], rcx
0x18000b453  mov     r8d, ecx; unsigned int
0x18000b456  mov     [rsp+0A8h+var_78], rbp; unsigned __int16 *
0x18000b45b  xor     ecx, ecx; struct _GUID *
0x18000b45d  mov     [rsp+0A8h+var_80], 1; int
0x18000b465  mov     qword ptr [rsp+0A8h+var_48], rax
0x18000b46a  mov     [rsp+0A8h+var_88], r13d; int
0x18000b46f  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x18000b474  mov     ebx, eax
0x18000b476  test    eax, eax
0x18000b478  jns     short loc_18000B485
0x18000b47a  mov     r9d, 5E4h
0x18000b480  jmp     loc_18000B55E
0x18000b485  cmp     esi, edi
0x18000b487  jnb     short loc_18000B4FF
0x18000b489  xor     ebp, ebp
0x18000b48b  test    r13d, r13d
0x18000b48e  setz    bpl
0x18000b492  mov     rax, [rsp+0A8h+arg_8]
0x18000b49a  xor     r9d, r9d; unsigned int
0x18000b49d  mov     [rsp+0A8h+var_50], r15; unsigned int *
0x18000b4a2  xor     r8d, r8d; unsigned int
0x18000b4a5  mov     [rsp+0A8h+var_58], r12; struct _SID_KEY_HEADER **
0x18000b4aa  mov     edx, edi; unsigned int
0x18000b4ac  mov     [rsp+0A8h+var_60], r14; int *
0x18000b4b1  xor     ecx, ecx; struct _GUID *
0x18000b4b3  mov     [rsp+0A8h+var_68], rax; unsigned __int16 *
0x18000b4b8  mov     eax, [rsp+0A8h+arg_18]
0x18000b4bf  mov     [rsp+0A8h+var_70], eax; unsigned int
0x18000b4c3  mov     rax, [rsp+0A8h+arg_10]
0x18000b4cb  mov     [rsp+0A8h+var_78], rax; unsigned __int16 *
0x18000b4d0  mov     [rsp+0A8h+var_80], 1; int
0x18000b4d8  mov     [rsp+0A8h+var_88], ebp; int
0x18000b4dc  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x18000b4e1  mov     ebx, eax
0x18000b4e3  test    eax, eax
0x18000b4e5  js      short loc_18000B4F1
0x18000b4e7  cmp     dword ptr [r14], 0
0x18000b4eb  jnz     loc_18000B573
0x18000b4f1  dec     edi
0x18000b4f3  cmp     esi, edi
0x18000b4f5  jb      short loc_18000B492
0x18000b4f7  mov     rbp, [rsp+0A8h+arg_10]
0x18000b4ff  mov     rcx, [rsp+0A8h+arg_8]
0x18000b507  xor     eax, eax
0x18000b509  mov     r9d, [rsp+0A8h+var_48]; unsigned int
0x18000b50e  test    r13d, r13d
0x18000b511  mov     r8d, [rsp+0A8h+var_40]; unsigned int
0x18000b516  mov     edx, esi; unsigned int
0x18000b518  mov     [rsp+0A8h+var_50], r15; unsigned int *
0x18000b51d  setz    al
0x18000b520  mov     [rsp+0A8h+var_58], r12; struct _SID_KEY_HEADER **
0x18000b525  mov     [rsp+0A8h+var_60], r14; int *
0x18000b52a  mov     [rsp+0A8h+var_68], rcx; unsigned __int16 *
0x18000b52f  mov     ecx, [rsp+0A8h+arg_18]
0x18000b536  mov     [rsp+0A8h+var_70], ecx; unsigned int
0x18000b53a  xor     ecx, ecx; struct _GUID *
0x18000b53c  mov     [rsp+0A8h+var_78], rbp; unsigned __int16 *
0x18000b541  mov     [rsp+0A8h+var_80], 1; int
0x18000b549  mov     [rsp+0A8h+var_88], eax; int
0x18000b54d  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x18000b552  mov     ebx, eax
0x18000b554  test    eax, eax
0x18000b556  jns     short loc_18000B573
0x18000b558  mov     r9d, 61Ch; unsigned int
0x18000b55e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b565  mov     ecx, eax; unsigned int
0x18000b567  lea     rdx, aHr; "hr"
0x18000b56e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b573  mov     eax, ebx
0x18000b575  mov     rbx, [rsp+0A8h+arg_0]
0x18000b57d  add     rsp, 70h
0x18000b581  pop     r15
0x18000b583  pop     r14
0x18000b585  pop     r13
0x18000b587  pop     r12
0x18000b589  pop     rdi
0x18000b58a  pop     rsi
0x18000b58b  pop     rbp
0x18000b58c  retn
```

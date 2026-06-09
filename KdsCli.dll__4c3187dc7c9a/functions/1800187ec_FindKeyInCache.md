# FindKeyInCache

- ea: `0x1800187ec`
- end: `0x1800189b1`
- name: `FindKeyInCache`
- size: `453`
- prototype: `__int64 __fastcall(_DWORD *, UCHAR *, ULONG, int, int, unsigned __int16 *, unsigned int, int *, struct _SID_KEY_HEADER **, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800196cc`
- `0x180019bec`

## callees

- `0x18000aef0`
- `0x18000b960`
- `0x180010010`
- `0x1800187ec`
- `0x18001a450`

## string_xrefs

- `0x18001896e`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall FindKeyInCache(
        _DWORD *a1,
        UCHAR *a2,
        ULONG a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        int *a8,
        struct _SID_KEY_HEADER **a9,
        unsigned int *a10,
        unsigned __int16 **a11,
        unsigned __int16 **a12)
{
  signed int SIDKeyCacheFolder; // eax
  unsigned __int16 *v14; // r12
  unsigned int v15; // ebx
  unsigned int v16; // r9d
  unsigned int v17; // esi
  unsigned int v18; // r14d
  unsigned int v19; // r15d
  unsigned int v21; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v22; // [rsp+64h] [rbp-1Dh] BYREF
  unsigned int v23; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int16 *v24; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp-9h] BYREF

  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  SIDKeyCacheFolder = GetSIDKeyCacheFolder(a2, a3, a4, &v25, &v24);
  v14 = v24;
  v15 = SIDKeyCacheFolder;
  if ( SIDKeyCacheFolder < 0 )
  {
    v16 = 237;
LABEL_12:
    SidKeyDebugTraceError(
      SIDKeyCacheFolder,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v16);
    goto LABEL_13;
  }
  if ( a1 )
  {
    v17 = a1[3];
    v18 = a1[4];
    v19 = a1[5];
  }
  else
  {
    GetCurrentIntervalID(0x53D1AC1000uLL, 0, &v21, &v22, &v23);
    v17 = v21;
    v18 = v22;
    v19 = v23;
  }
  SIDKeyCacheFolder = FindAndReadSIDKeyInCache(
                        (struct _GUID *)(-(__int64)(a1 != 0) & (unsigned __int64)(a1 + 6)),
                        v17,
                        v18,
                        v19,
                        0,
                        a5,
                        a6,
                        a7,
                        v14,
                        a8,
                        a9,
                        a10);
  v15 = SIDKeyCacheFolder;
  if ( SIDKeyCacheFolder < 0 )
  {
    v16 = 274;
    goto LABEL_12;
  }
  if ( !*a8 && !a1 )
  {
    SIDKeyCacheFolder = FindAndReadSIDKeyInCache(0, v17, v18, v19, 1, a5, a6, a7, v14, a8, a9, a10);
    v15 = SIDKeyCacheFolder;
    if ( SIDKeyCacheFolder < 0 )
    {
      v16 = 297;
      goto LABEL_12;
    }
  }
LABEL_13:
  *a11 = v14;
  *a12 = v25;
  return v15;
}

```

## disassembly

```asm
0x1800187ec  push    rbp
0x1800187ee  push    rbx
0x1800187ef  push    rsi
0x1800187f0  push    rdi
0x1800187f1  push    r12
0x1800187f3  push    r13
0x1800187f5  push    r14
0x1800187f7  push    r15
0x1800187f9  lea     rbp, [rsp-7]
0x1800187fe  sub     rsp, 88h
0x180018805  xor     esi, esi
0x180018807  mov     rdi, rcx
0x18001880a  mov     eax, r9d
0x18001880d  mov     [rbp+3Fh+var_60], esi
0x180018810  mov     r10d, r8d
0x180018813  mov     [rbp+3Fh+var_5C], esi
0x180018816  mov     r11, rdx
0x180018819  mov     [rbp+3Fh+var_58], esi
0x18001881c  lea     rcx, [rbp+3Fh+var_50]
0x180018820  mov     [rbp+3Fh+var_50], rsi
0x180018824  mov     [rsp+0C0h+var_A0], rcx; unsigned __int16 **
0x180018829  lea     r9, [rbp+3Fh+var_48]; unsigned __int16 **
0x18001882d  mov     rcx, r11; pbInput
0x180018830  mov     [rbp+3Fh+var_48], rsi
0x180018834  mov     r8d, eax; int
0x180018837  mov     edx, r10d; cbInput
0x18001883a  call    ?GetSIDKeyCacheFolder@@YAJPEAEKHPEAPEAG1@Z; GetSIDKeyCacheFolder(uchar *,ulong,int,ushort * *,ushort * *)
0x18001883f  mov     r12, [rbp+3Fh+var_50]
0x180018843  mov     ebx, eax
0x180018845  test    eax, eax
0x180018847  jns     short loc_180018854
0x180018849  mov     r9d, 0EDh
0x18001884f  jmp     loc_18001896E
0x180018854  test    rdi, rdi
0x180018857  jnz     short loc_180018888
0x180018859  lea     rax, [rbp+3Fh+var_58]
0x18001885d  xor     edx, edx; int
0x18001885f  lea     r9, [rbp+3Fh+var_5C]; unsigned int *
0x180018863  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x180018868  lea     r8, [rbp+3Fh+var_60]; unsigned int *
0x18001886c  mov     rcx, 53D1AC1000h; unsigned __int64
0x180018876  call    ?GetCurrentIntervalID@@YAX_KHPEAK11@Z; GetCurrentIntervalID(unsigned __int64,int,ulong *,ulong *,ulong *)
0x18001887b  mov     esi, [rbp+3Fh+var_60]
0x18001887e  mov     r14d, [rbp+3Fh+var_5C]
0x180018882  mov     r15d, [rbp+3Fh+var_58]
0x180018886  jmp     short loc_180018893
0x180018888  mov     esi, [rdi+0Ch]
0x18001888b  mov     r14d, [rdi+10h]
0x18001888f  mov     r15d, [rdi+14h]
0x180018893  mov     r13, [rbp+3Fh+arg_38]
0x18001889a  lea     rcx, [rdi+18h]
0x18001889e  mov     rax, rdi
0x1800188a1  mov     r9d, r15d; unsigned int
0x1800188a4  neg     rax
0x1800188a7  mov     r8d, r14d; unsigned int
0x1800188aa  mov     rax, [rbp+3Fh+arg_48]
0x1800188b1  mov     edx, esi; unsigned int
0x1800188b3  mov     [rsp+0C0h+var_68], rax; unsigned int *
0x1800188b8  sbb     r10, r10
0x1800188bb  mov     rax, [rbp+3Fh+arg_40]
0x1800188c2  and     rcx, r10; struct _GUID *
0x1800188c5  mov     [rsp+0C0h+var_70], rax; struct _SID_KEY_HEADER **
0x1800188ca  mov     eax, [rbp+3Fh+arg_30]
0x1800188cd  mov     [rsp+0C0h+var_78], r13; int *
0x1800188d2  mov     [rsp+0C0h+var_80], r12; unsigned __int16 *
0x1800188d7  mov     [rsp+0C0h+var_88], eax; unsigned int
0x1800188db  mov     rax, [rbp+3Fh+arg_28]
0x1800188df  mov     [rsp+0C0h+var_90], rax; unsigned __int16 *
0x1800188e4  mov     eax, [rbp+3Fh+arg_20]
0x1800188e7  mov     [rsp+0C0h+var_98], eax; int
0x1800188eb  mov     dword ptr [rsp+0C0h+var_A0], 0; int
0x1800188f3  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x1800188f8  mov     ebx, eax
0x1800188fa  test    eax, eax
0x1800188fc  jns     short loc_180018906
0x1800188fe  mov     r9d, 112h
0x180018904  jmp     short loc_18001896E
0x180018906  cmp     dword ptr [r13+0], 0
0x18001890b  jnz     short loc_180018983
0x18001890d  test    rdi, rdi
0x180018910  jnz     short loc_180018983
0x180018912  mov     rax, [rbp+3Fh+arg_48]
0x180018919  mov     r9d, r15d; unsigned int
0x18001891c  mov     [rsp+0C0h+var_68], rax; unsigned int *
0x180018921  mov     r8d, r14d; unsigned int
0x180018924  mov     rax, [rbp+3Fh+arg_40]
0x18001892b  mov     edx, esi; unsigned int
0x18001892d  mov     [rsp+0C0h+var_70], rax; struct _SID_KEY_HEADER **
0x180018932  xor     ecx, ecx; struct _GUID *
0x180018934  mov     eax, [rbp+3Fh+arg_30]
0x180018937  mov     [rsp+0C0h+var_78], r13; int *
0x18001893c  mov     [rsp+0C0h+var_80], r12; unsigned __int16 *
0x180018941  mov     [rsp+0C0h+var_88], eax; unsigned int
0x180018945  mov     rax, [rbp+3Fh+arg_28]
0x180018949  mov     [rsp+0C0h+var_90], rax; unsigned __int16 *
0x18001894e  mov     eax, [rbp+3Fh+arg_20]
0x180018951  mov     [rsp+0C0h+var_98], eax; int
0x180018955  mov     dword ptr [rsp+0C0h+var_A0], 1; int
0x18001895d  call    ?FindAndReadSIDKeyInCache@@YAJPEAU_GUID@@KKKHHPEBGK1PEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindAndReadSIDKeyInCache(_GUID *,ulong,ulong,ulong,int,int,ushort const *,ulong,ushort const *,int *,_SID_KEY_HEADER * *,ulong *)
0x180018962  mov     ebx, eax
0x180018964  test    eax, eax
0x180018966  jns     short loc_180018983
0x180018968  mov     r9d, 129h; unsigned int
0x18001896e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018975  mov     ecx, eax; unsigned int
0x180018977  lea     rdx, aHr; "hr"
0x18001897e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018983  mov     rax, [rbp+3Fh+arg_50]
0x18001898a  mov     rcx, [rbp+3Fh+arg_58]
0x180018991  mov     [rax], r12
0x180018994  mov     rax, [rbp+3Fh+var_48]
0x180018998  mov     [rcx], rax
0x18001899b  mov     eax, ebx
0x18001899d  add     rsp, 88h
0x1800189a4  pop     r15
0x1800189a6  pop     r14
0x1800189a8  pop     r13
0x1800189aa  pop     r12
0x1800189ac  pop     rdi
0x1800189ad  pop     rsi
0x1800189ae  pop     rbx
0x1800189af  pop     rbp
0x1800189b0  retn
```

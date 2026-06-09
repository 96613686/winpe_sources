# CSyncChangeWrapper_CreateInstance(IdParameters *,uchar *,uchar *,ISyncKnowledge *,ulong,ISyncKnowledge * *,ISyncKnowledge * *,ISyncKnowledge *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,CSyncChangeWrapper * *)

- ea: `0x180066f84`
- end: `0x180067137`
- name: `?CSyncChangeWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAE1PEAUISyncKnowledge@@KPEAPEAU2@3222PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@PEAPEAVCSyncChangeWrapper@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct IdParameters *, unsigned __int8 *, unsigned __int8 *, struct ISyncKnowledge *, unsigned int, struct ISyncKnowledge **, struct ISyncKnowledge **, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncFilterInfo *, struct CSyncChangeWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180063e18`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180066018`
- `0x180066f84`
- `0x18006b064`
- `0x180094010`

## string_xrefs

- `0x180066fc5`: `CSyncChangeWrapper_CreateInstance`
- `0x180067107`: `CSyncChangeWrapper_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper_CreateInstance(
        struct IdParameters *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        struct ISyncKnowledge *a4,
        unsigned int a5,
        struct ISyncKnowledge **a6,
        struct ISyncKnowledge **a7,
        struct ISyncKnowledge *a8,
        struct ISyncKnowledge *a9,
        struct ISyncKnowledge *a10,
        struct IForgottenKnowledge *a11,
        struct ISyncFilterInfo *a12,
        struct CSyncChangeWrapper **a13)
{
  int v15; // r15d
  PVOID *v17; // rcx
  int v18; // edi
  CSyncChangeWrapper *v19; // rax
  CSyncChangeWrapper *v20; // rax
  struct CSyncChangeWrapper *v21; // rbx

  v15 = (int)a2;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      193,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper_CreateInstance");
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = -2147467261;
  if ( a1 && a13 )
  {
    *a13 = 0;
    v18 = -2147024882;
    v19 = (CSyncChangeWrapper *)SeAlloc(0x1F0u);
    if ( v19 )
    {
      v20 = CSyncChangeWrapper::CSyncChangeWrapper(v19, a1);
      v21 = v20;
      if ( v20 )
      {
        v18 = CSyncChangeWrapper::Init(
                (_DWORD)v20,
                0,
                0,
                v15,
                (__int64)a3,
                (__int64)a4,
                a5,
                0,
                (__int64)a6,
                (__int64)a7,
                (__int64)a8,
                (__int64)a9,
                (__int64)a10,
                (__int64)a11,
                (__int64)a12);
        if ( v18 >= 0 )
        {
          v18 = 0;
          (*(void (__fastcall **)(struct CSyncChangeWrapper *))(*(_QWORD *)v21 + 8LL))(v21);
          *a13 = v21;
        }
        (*(void (__fastcall **)(struct CSyncChangeWrapper *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 && *((_BYTE *)v17 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v17[2],
      194,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper_CreateInstance",
      v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180066f84  push    rbx
0x180066f86  push    rbp
0x180066f87  push    rsi
0x180066f88  push    rdi
0x180066f89  push    r12
0x180066f8b  push    r14
0x180066f8d  push    r15
0x180066f8f  sub     rsp, 80h
0x180066f96  mov     rbp, r9
0x180066f99  mov     r14, r8
0x180066f9c  mov     r15, rdx
0x180066f9f  mov     rbx, rcx
0x180066fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fa9  lea     r12, WPP_GLOBAL_Control
0x180066fb0  cmp     rcx, r12
0x180066fb3  jz      short loc_180066FE4
0x180066fb5  test    byte ptr [rcx+1Ch], 8
0x180066fb9  jz      short loc_180066FE4
0x180066fbb  cmp     byte ptr [rcx+19h], 5
0x180066fbf  jb      short loc_180066FE4
0x180066fc1  mov     rcx, [rcx+10h]
0x180066fc5  lea     r9, aCsyncchangewra_43; "CSyncChangeWrapper_CreateInstance"
0x180066fcc  mov     edx, 0C1h
0x180066fd1  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180066fd8  call    WPP_SF_s
0x180066fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fe4  mov     edi, 80004003h
0x180066fe9  test    rbx, rbx
0x180066fec  jz      loc_1800670F2
0x180066ff2  mov     rsi, [rsp+0B8h+arg_60]
0x180066ffa  test    rsi, rsi
0x180066ffd  jz      loc_1800670F2
0x180067003  mov     ecx, 1F0h; unsigned __int64
0x180067008  mov     qword ptr [rsi], 0
0x18006700f  mov     edi, 8007000Eh
0x180067014  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180067019  test    rax, rax
0x18006701c  jz      loc_1800670EB
0x180067022  mov     rdx, rbx; struct IdParameters *
0x180067025  mov     rcx, rax; this
0x180067028  call    ??0CSyncChangeWrapper@@QEAA@PEAVIdParameters@@@Z; CSyncChangeWrapper::CSyncChangeWrapper(IdParameters *)
0x18006702d  mov     rbx, rax
0x180067030  test    rax, rax
0x180067033  jz      loc_1800670EB
0x180067039  mov     rax, [rsp+0B8h+arg_58]
0x180067041  mov     r9, r15
0x180067044  mov     [rsp+0B8h+var_48], rax
0x180067049  xor     r8d, r8d
0x18006704c  mov     rax, [rsp+0B8h+arg_50]
0x180067054  xor     edx, edx
0x180067056  mov     [rsp+0B8h+var_50], rax
0x18006705b  mov     rcx, rbx
0x18006705e  mov     rax, [rsp+0B8h+arg_48]
0x180067066  mov     [rsp+0B8h+var_58], rax
0x18006706b  mov     rax, [rsp+0B8h+arg_40]
0x180067073  mov     [rsp+0B8h+var_60], rax
0x180067078  mov     rax, [rsp+0B8h+arg_38]
0x180067080  mov     [rsp+0B8h+var_68], rax
0x180067085  mov     rax, [rsp+0B8h+arg_30]
0x18006708d  mov     [rsp+0B8h+var_70], rax
0x180067092  mov     rax, [rsp+0B8h+arg_28]
0x18006709a  mov     [rsp+0B8h+var_78], rax
0x18006709f  mov     eax, [rsp+0B8h+arg_20]
0x1800670a6  mov     [rsp+0B8h+var_80], 0
0x1800670af  mov     [rsp+0B8h+var_88], eax
0x1800670b3  mov     [rsp+0B8h+var_90], rbp
0x1800670b8  mov     [rsp+0B8h+var_98], r14
0x1800670bd  call    ?Init@CSyncChangeWrapper@@QEAAJPEAUISyncChange@@HPEAE1PEAUISyncKnowledge@@KPEAV?$RefCountedHashTable@KK@@PEAPEAU3@4222PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@@Z; CSyncChangeWrapper::Init(ISyncChange *,int,uchar *,uchar *,ISyncKnowledge *,ulong,RefCountedHashTable<ulong,ulong> *,ISyncKnowledge * *,ISyncKnowledge * *,ISyncKnowledge *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *)
0x1800670c2  mov     edi, eax
0x1800670c4  test    eax, eax
0x1800670c6  js      short loc_1800670DC
0x1800670c8  mov     rax, [rbx]
0x1800670cb  xor     edi, edi
0x1800670cd  mov     rcx, rbx
0x1800670d0  mov     rax, [rax+8]
0x1800670d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670d9  mov     [rsi], rbx
0x1800670dc  mov     rax, [rbx]
0x1800670df  mov     rcx, rbx
0x1800670e2  mov     rax, [rax+10h]
0x1800670e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800670f2  cmp     rcx, r12
0x1800670f5  jz      short loc_180067123
0x1800670f7  test    byte ptr [rcx+1Ch], 8
0x1800670fb  jz      short loc_180067123
0x1800670fd  cmp     byte ptr [rcx+19h], 5
0x180067101  jb      short loc_180067123
0x180067103  mov     rcx, [rcx+10h]
0x180067107  lea     r9, aCsyncchangewra_43; "CSyncChangeWrapper_CreateInstance"
0x18006710e  mov     edx, 0C2h
0x180067113  mov     dword ptr [rsp+0B8h+var_98], edi
0x180067117  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006711e  call    WPP_SF_sD
0x180067123  mov     eax, edi
0x180067125  add     rsp, 80h
0x18006712c  pop     r15
0x18006712e  pop     r14
0x180067130  pop     r12
0x180067132  pop     rdi
0x180067133  pop     rsi
0x180067134  pop     rbp
0x180067135  pop     rbx
0x180067136  retn
```

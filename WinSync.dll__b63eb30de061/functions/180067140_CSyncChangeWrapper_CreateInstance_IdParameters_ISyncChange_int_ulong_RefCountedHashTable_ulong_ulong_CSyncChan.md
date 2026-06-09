# CSyncChangeWrapper_CreateInstance(IdParameters *,ISyncChange *,int,ulong,RefCountedHashTable<ulong,ulong> *,CSyncChangeWrapper * *)

- ea: `0x180067140`
- end: `0x1800672e5`
- name: `?CSyncChangeWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncChange@@HKPEAV?$RefCountedHashTable@KK@@PEAPEAVCSyncChangeWrapper@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct IdParameters *, __int64, int, int, __int64, CSyncChangeWrapper **)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x1800383f4`
- `0x18003a64c`
- `0x18003c0d8`
- `0x180041720`
- `0x18005faac`
- `0x180063b8c`
- `0x180067748`
- `0x18006d9c8`
- `0x18006e66c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180066018`
- `0x180067140`
- `0x18006b064`
- `0x180094010`

## string_xrefs

- `0x180067181`: `CSyncChangeWrapper_CreateInstance`
- `0x1800672b5`: `CSyncChangeWrapper_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper_CreateInstance(
        struct IdParameters *a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        CSyncChangeWrapper **a6)
{
  PVOID *v10; // rcx
  int v11; // edi
  CSyncChangeWrapper *v12; // rax
  CSyncChangeWrapper *v13; // rbx

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper_CreateInstance");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = -2147467261;
  if ( a1 && a6 && a2 )
  {
    *a6 = 0;
    v11 = -2147024882;
    v12 = (CSyncChangeWrapper *)SeAlloc(0x1F0u);
    if ( v12 )
    {
      v13 = CSyncChangeWrapper::CSyncChangeWrapper(v12, a1);
      if ( v13 )
      {
        v11 = CSyncChangeWrapper::Init((_DWORD)v13, a2, a3, 0, 0, 0, a4, a5, 0, 0, 0, 0, 0, 0, 0);
        if ( v11 >= 0 )
        {
          (*(void (__fastcall **)(CSyncChangeWrapper *))(*(_QWORD *)v13 + 8LL))(v13);
          *a6 = v13;
        }
        (*(void (__fastcall **)(CSyncChangeWrapper *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v10[2],
      192,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper_CreateInstance",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180067140  push    rbx
0x180067142  push    rbp
0x180067143  push    rsi
0x180067144  push    rdi
0x180067145  push    r13
0x180067147  push    r14
0x180067149  push    r15
0x18006714b  sub     rsp, 80h
0x180067152  mov     r14d, r9d
0x180067155  mov     r15d, r8d
0x180067158  mov     rbp, rdx
0x18006715b  mov     rbx, rcx
0x18006715e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067165  lea     r13, WPP_GLOBAL_Control
0x18006716c  cmp     rcx, r13
0x18006716f  jz      short loc_1800671A0
0x180067171  test    byte ptr [rcx+1Ch], 8
0x180067175  jz      short loc_1800671A0
0x180067177  cmp     byte ptr [rcx+19h], 5
0x18006717b  jb      short loc_1800671A0
0x18006717d  mov     rcx, [rcx+10h]
0x180067181  lea     r9, aCsyncchangewra_43; "CSyncChangeWrapper_CreateInstance"
0x180067188  mov     edx, 0BFh
0x18006718d  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180067194  call    WPP_SF_s
0x180067199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800671a0  mov     edi, 80004003h
0x1800671a5  test    rbx, rbx
0x1800671a8  jz      loc_1800672A0
0x1800671ae  mov     rsi, [rsp+0B8h+arg_28]
0x1800671b6  test    rsi, rsi
0x1800671b9  jz      loc_1800672A0
0x1800671bf  test    rbp, rbp
0x1800671c2  jz      loc_1800672A0
0x1800671c8  mov     ecx, 1F0h; unsigned __int64
0x1800671cd  mov     qword ptr [rsi], 0
0x1800671d4  mov     edi, 8007000Eh
0x1800671d9  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800671de  test    rax, rax
0x1800671e1  jz      loc_180067299
0x1800671e7  mov     rdx, rbx; struct IdParameters *
0x1800671ea  mov     rcx, rax; this
0x1800671ed  call    ??0CSyncChangeWrapper@@QEAA@PEAVIdParameters@@@Z; CSyncChangeWrapper::CSyncChangeWrapper(IdParameters *)
0x1800671f2  mov     rbx, rax
0x1800671f5  test    rax, rax
0x1800671f8  jz      loc_180067299
0x1800671fe  mov     rax, [rsp+0B8h+arg_20]
0x180067206  xor     r9d, r9d
0x180067209  mov     [rsp+0B8h+var_48], 0
0x180067212  mov     r8d, r15d
0x180067215  mov     [rsp+0B8h+var_50], 0
0x18006721e  mov     rdx, rbp
0x180067221  mov     [rsp+0B8h+var_58], 0
0x18006722a  mov     rcx, rbx
0x18006722d  mov     [rsp+0B8h+var_60], 0
0x180067236  mov     [rsp+0B8h+var_68], 0
0x18006723f  mov     [rsp+0B8h+var_70], 0
0x180067248  mov     [rsp+0B8h+var_78], 0
0x180067251  mov     [rsp+0B8h+var_80], rax
0x180067256  mov     [rsp+0B8h+var_88], r14d
0x18006725b  mov     [rsp+0B8h+var_90], 0
0x180067264  mov     [rsp+0B8h+var_98], 0
0x18006726d  call    ?Init@CSyncChangeWrapper@@QEAAJPEAUISyncChange@@HPEAE1PEAUISyncKnowledge@@KPEAV?$RefCountedHashTable@KK@@PEAPEAU3@4222PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@@Z; CSyncChangeWrapper::Init(ISyncChange *,int,uchar *,uchar *,ISyncKnowledge *,ulong,RefCountedHashTable<ulong,ulong> *,ISyncKnowledge * *,ISyncKnowledge * *,ISyncKnowledge *,ISyncKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *)
0x180067272  mov     edi, eax
0x180067274  test    eax, eax
0x180067276  js      short loc_18006728A
0x180067278  mov     rcx, [rbx]
0x18006727b  mov     rax, [rcx+8]
0x18006727f  mov     rcx, rbx
0x180067282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067287  mov     [rsi], rbx
0x18006728a  mov     rcx, [rbx]
0x18006728d  mov     rax, [rcx+10h]
0x180067291  mov     rcx, rbx
0x180067294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800672a0  cmp     rcx, r13
0x1800672a3  jz      short loc_1800672D1
0x1800672a5  test    byte ptr [rcx+1Ch], 8
0x1800672a9  jz      short loc_1800672D1
0x1800672ab  cmp     byte ptr [rcx+19h], 5
0x1800672af  jb      short loc_1800672D1
0x1800672b1  mov     rcx, [rcx+10h]
0x1800672b5  lea     r9, aCsyncchangewra_43; "CSyncChangeWrapper_CreateInstance"
0x1800672bc  mov     edx, 0C0h
0x1800672c1  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800672c5  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x1800672cc  call    WPP_SF_sD
0x1800672d1  mov     eax, edi
0x1800672d3  add     rsp, 80h
0x1800672da  pop     r15
0x1800672dc  pop     r14
0x1800672de  pop     r13
0x1800672e0  pop     rdi
0x1800672e1  pop     rsi
0x1800672e2  pop     rbp
0x1800672e3  pop     rbx
0x1800672e4  retn
```

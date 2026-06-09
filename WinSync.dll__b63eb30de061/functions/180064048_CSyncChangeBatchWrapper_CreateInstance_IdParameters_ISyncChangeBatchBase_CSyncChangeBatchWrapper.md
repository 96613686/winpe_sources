# CSyncChangeBatchWrapper_CreateInstance(IdParameters *,ISyncChangeBatchBase *,CSyncChangeBatchWrapper * *)

- ea: `0x180064048`
- end: `0x1800641ae`
- name: `?CSyncChangeBatchWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncChangeBatchBase@@PEAPEAVCSyncChangeBatchWrapper@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(struct IdParameters *, struct ISyncChangeBatchBase *, struct CSyncChangeBatchWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800347e0`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180063ad4`
- `0x180064048`
- `0x180065178`
- `0x180094010`

## string_xrefs

- `0x180064081`: `CSyncChangeBatchWrapper_CreateInstance`
- `0x180064183`: `CSyncChangeBatchWrapper_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper_CreateInstance(
        struct IdParameters *a1,
        struct ISyncChangeBatchBase *a2,
        struct CSyncChangeBatchWrapper **a3)
{
  PVOID *v6; // rcx
  int v7; // edi
  _QWORD *v8; // rbx
  void *v9; // rax
  CSyncChangeBatchWrapper *v10; // rax
  struct CSyncChangeBatchWrapper *v11; // rsi

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper_CreateInstance");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = -2147467261;
  if ( a1 && a3 )
  {
    v7 = -2147024882;
    v8 = SeAlloc(0x28u);
    if ( v8 )
    {
      v8[2] = 0;
      *v8 = &CollectionManager<CSyncChangeUnitWrapper>::`vftable';
      *((_DWORD *)v8 + 2) = 1;
      v8[3] = 0;
      *((_DWORD *)v8 + 8) = 0;
      _InterlockedIncrement(&g_cRefThisDll);
      v9 = SeAlloc(0x70u);
      if ( v9 )
      {
        v10 = (CSyncChangeBatchWrapper *)CSyncChangeBatchWrapper::CSyncChangeBatchWrapper(v9, a1, v8, a2);
        v11 = v10;
        if ( v10 )
        {
          v7 = CSyncChangeBatchWrapper::Init(v10);
          if ( v7 >= 0 )
          {
            (*(void (__fastcall **)(struct CSyncChangeBatchWrapper *))(*(_QWORD *)v11 + 8LL))(v11);
            *a3 = v11;
          }
          (*(void (__fastcall **)(struct CSyncChangeBatchWrapper *))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      60,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper_CreateInstance",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064048  push    rbx
0x18006404a  push    rbp
0x18006404b  push    rsi
0x18006404c  push    rdi
0x18006404d  push    r12
0x18006404f  push    r14
0x180064051  sub     rsp, 38h
0x180064055  mov     r14, r8
0x180064058  mov     rbp, rdx
0x18006405b  mov     rsi, rcx
0x18006405e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064065  lea     r12, WPP_GLOBAL_Control
0x18006406c  cmp     rcx, r12
0x18006406f  jz      short loc_1800640A0
0x180064071  test    byte ptr [rcx+1Ch], 8
0x180064075  jz      short loc_1800640A0
0x180064077  cmp     byte ptr [rcx+19h], 5
0x18006407b  jb      short loc_1800640A0
0x18006407d  mov     rcx, [rcx+10h]
0x180064081  lea     r9, aCsyncchangebat_80; "CSyncChangeBatchWrapper_CreateInstance"
0x180064088  mov     edx, 3Bh ; ';'
0x18006408d  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064094  call    WPP_SF_s
0x180064099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640a0  mov     edi, 80004003h
0x1800640a5  test    rsi, rsi
0x1800640a8  jz      loc_18006416E
0x1800640ae  test    r14, r14
0x1800640b1  jz      loc_18006416E
0x1800640b7  mov     ecx, 28h ; '('; unsigned __int64
0x1800640bc  mov     edi, 8007000Eh
0x1800640c1  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800640c6  mov     rbx, rax
0x1800640c9  test    rax, rax
0x1800640cc  jz      loc_180064167
0x1800640d2  lea     rax, ??_7?$CollectionManager@VCSyncChangeUnitWrapper@@@@6B@; const CollectionManager<CSyncChangeUnitWrapper>::`vftable'
0x1800640d9  mov     qword ptr [rbx+10h], 0
0x1800640e1  mov     [rbx], rax
0x1800640e4  mov     dword ptr [rbx+8], 1
0x1800640eb  mov     qword ptr [rbx+18h], 0
0x1800640f3  mov     dword ptr [rbx+20h], 0
0x1800640fa  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x180064101  mov     ecx, 70h ; 'p'; unsigned __int64
0x180064106  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18006410b  test    rax, rax
0x18006410e  jz      short loc_180064158
0x180064110  mov     r9, rbp
0x180064113  mov     r8, rbx
0x180064116  mov     rdx, rsi
0x180064119  mov     rcx, rax
0x18006411c  call    ??0CSyncChangeBatchWrapper@@QEAA@PEAVIdParameters@@PEAV?$CollectionManager@VCSyncChangeWrapper@@@@PEAUISyncChangeBatchBase@@@Z; CSyncChangeBatchWrapper::CSyncChangeBatchWrapper(IdParameters *,CollectionManager<CSyncChangeWrapper> *,ISyncChangeBatchBase *)
0x180064121  mov     rsi, rax
0x180064124  test    rax, rax
0x180064127  jz      short loc_180064158
0x180064129  mov     rcx, rax; this
0x18006412c  call    ?Init@CSyncChangeBatchWrapper@@QEAAJXZ; CSyncChangeBatchWrapper::Init(void)
0x180064131  mov     edi, eax
0x180064133  test    eax, eax
0x180064135  js      short loc_180064149
0x180064137  mov     rcx, [rsi]
0x18006413a  mov     rax, [rcx+8]
0x18006413e  mov     rcx, rsi
0x180064141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064146  mov     [r14], rsi
0x180064149  mov     rcx, [rsi]
0x18006414c  mov     rax, [rcx+10h]
0x180064150  mov     rcx, rsi
0x180064153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064158  mov     rax, [rbx]
0x18006415b  mov     rcx, rbx
0x18006415e  mov     rax, [rax+10h]
0x180064162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064167  mov     rcx, cs:WPP_GLOBAL_Control
0x18006416e  cmp     rcx, r12
0x180064171  jz      short loc_18006419F
0x180064173  test    byte ptr [rcx+1Ch], 8
0x180064177  jz      short loc_18006419F
0x180064179  cmp     byte ptr [rcx+19h], 5
0x18006417d  jb      short loc_18006419F
0x18006417f  mov     rcx, [rcx+10h]
0x180064183  lea     r9, aCsyncchangebat_80; "CSyncChangeBatchWrapper_CreateInstance"
0x18006418a  mov     edx, 3Ch ; '<'
0x18006418f  mov     [rsp+68h+var_48], edi
0x180064193  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x18006419a  call    WPP_SF_sD
0x18006419f  mov     eax, edi
0x1800641a1  add     rsp, 38h
0x1800641a5  pop     r14
0x1800641a7  pop     r12
0x1800641a9  pop     rdi
0x1800641aa  pop     rsi
0x1800641ab  pop     rbp
0x1800641ac  pop     rbx
0x1800641ad  retn
```

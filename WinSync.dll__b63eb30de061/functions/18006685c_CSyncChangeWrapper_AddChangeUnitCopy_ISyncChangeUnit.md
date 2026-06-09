# CSyncChangeWrapper::AddChangeUnitCopy(ISyncChangeUnit *)

- ea: `0x18006685c`
- end: `0x180066b10`
- name: `?AddChangeUnitCopy@CSyncChangeWrapper@@QEAAJPEAUISyncChangeUnit@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct ISyncChangeUnit *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005cd9c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18002dc04`
- `0x18002dc5c`
- `0x180066680`
- `0x18006685c`
- `0x18007198c`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x1800668a8`: `CSyncChangeWrapper::AddChangeUnitCopy`
- `0x180066ac6`: `CSyncChangeWrapper::AddChangeUnitCopy`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::AddChangeUnitCopy(CSyncChangeWrapper *this, struct ISyncChangeUnit *a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  unsigned __int8 *v7; // rsi
  int v8; // eax
  CSyncChangeUnitWrapper *v9; // rax
  CSyncChangeUnitWrapper *v10; // rdi
  PVOID *v11; // rcx
  __int128 v12; // xmm0
  unsigned int v14; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int8 *v15; // [rsp+38h] [rbp-28h] BYREF
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      153,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::AddChangeUnitCopy");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 53);
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v5 = IdParameterPair::AllocateId((IdParameterPair *)(v6 + 32), &v15, &v14);
    if ( v5 == 1 )
    {
      v7 = v15;
      v8 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, unsigned __int8 *, unsigned int *))a2->lpVtbl->GetChangeUnitId)(
             a2,
             v15,
             &v14);
      v5 = v8;
      if ( v8 != -2147024662 )
      {
        if ( v8 >= 0 )
          v5 = -2147217379;
        goto LABEL_28;
      }
      v5 = IdParameterPair::AllocateId((IdParameterPair *)(*((_QWORD *)this + 53) + 32LL), &v15, v14);
    }
    v7 = v15;
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, unsigned __int8 *, unsigned int *))a2->lpVtbl->GetChangeUnitId)(
             a2,
             v15,
             &v14);
      if ( v5 >= 0 )
      {
        v5 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, _QWORD, __int128 *))a2->lpVtbl->GetChangeUnitVersion)(
               a2,
               *((_QWORD *)this + 13),
               &v16);
        if ( v5 >= 0 )
        {
          v5 = -2147024882;
          v9 = (CSyncChangeUnitWrapper *)SeAlloc(0x78u);
          if ( v9 )
          {
            v10 = CSyncChangeUnitWrapper::CSyncChangeUnitWrapper(v9, *((struct IdParameters **)this + 53));
            if ( v10 )
            {
              v11 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
                  "CSyncChangeUnitWrapper::Init");
                v11 = (PVOID *)WPP_GLOBAL_Control;
              }
              v5 = -2147467261;
              if ( v7 && v10 != (CSyncChangeUnitWrapper *)-24LL )
              {
                _InterlockedIncrement((volatile signed __int32 *)v7 - 1);
                *((_QWORD *)v10 + 3) = v7;
                v12 = v16;
                *((_QWORD *)v10 + 13) = this;
                *((_OWORD *)v10 + 2) = v12;
                _InterlockedIncrement((volatile signed __int32 *)this + 15);
                v11 = (PVOID *)WPP_GLOBAL_Control;
                v5 = 0;
              }
              if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
                WPP_SF_sD(
                  (unsigned int)v11[2],
                  16,
                  (unsigned int)WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
                  (unsigned int)"CSyncChangeUnitWrapper::Init",
                  v5);
              if ( v5 >= 0 )
                v5 = CSyncChangeWrapper::AddChangeUnit(this, v10);
              (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v10 + 16LL))(v10);
            }
          }
        }
      }
    }
LABEL_28:
    IdParameters::FreeId(v7);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      154,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::AddChangeUnitCopy",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006685c  mov     [rsp-18h+arg_10], rbx
0x180066861  mov     [rsp-18h+arg_18], rsi
0x180066866  push    rbp
0x180066867  push    rdi
0x180066868  push    r14
0x18006686a  mov     rbp, rsp
0x18006686d  sub     rsp, 60h
0x180066871  mov     rax, cs:__security_cookie
0x180066878  xor     rax, rsp
0x18006687b  mov     [rbp+var_10], rax
0x18006687f  mov     rdi, rdx
0x180066882  mov     r14, rcx
0x180066885  mov     rcx, cs:WPP_GLOBAL_Control
0x18006688c  lea     rax, WPP_GLOBAL_Control
0x180066893  cmp     rcx, rax
0x180066896  jz      short loc_1800668C7
0x180066898  test    byte ptr [rcx+1Ch], 8
0x18006689c  jz      short loc_1800668C7
0x18006689e  cmp     byte ptr [rcx+19h], 5
0x1800668a2  jb      short loc_1800668C7
0x1800668a4  mov     rcx, [rcx+10h]
0x1800668a8  lea     r9, aCsyncchangewra_86; "CSyncChangeWrapper::AddChangeUnitCopy"
0x1800668af  mov     edx, 99h
0x1800668b4  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x1800668bb  call    WPP_SF_s
0x1800668c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668c7  mov     ebx, 80004003h
0x1800668cc  test    rdi, rdi
0x1800668cf  jz      loc_180066AAA
0x1800668d5  mov     rcx, [r14+1A8h]
0x1800668dc  lea     r8, [rbp+var_30]; unsigned int *
0x1800668e0  xorps   xmm0, xmm0
0x1800668e3  mov     [rbp+var_30], 0
0x1800668ea  add     rcx, 20h ; ' '; this
0x1800668ee  mov     [rbp+var_28], 0
0x1800668f6  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x1800668fa  movups  [rbp+var_20], xmm0
0x1800668fe  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEPEAK@Z; IdParameterPair::AllocateId(uchar * *,ulong *)
0x180066903  mov     ebx, eax
0x180066905  cmp     eax, 1
0x180066908  jnz     short loc_18006694C
0x18006690a  mov     rax, [rdi]
0x18006690d  lea     r8, [rbp+var_30]
0x180066911  mov     rsi, [rbp+var_28]
0x180066915  mov     rcx, rdi
0x180066918  mov     rdx, rsi
0x18006691b  mov     rax, [rax+20h]
0x18006691f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066924  mov     ebx, eax
0x180066926  cmp     eax, 800700EAh
0x18006692b  jnz     loc_180066B05
0x180066931  mov     rcx, [r14+1A8h]
0x180066938  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x18006693c  movzx   r8d, word ptr [rbp+var_30]; unsigned __int16
0x180066941  add     rcx, 20h ; ' '; this
0x180066945  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEG@Z; IdParameterPair::AllocateId(uchar * *,ushort)
0x18006694a  mov     ebx, eax
0x18006694c  mov     rsi, [rbp+var_28]
0x180066950  test    ebx, ebx
0x180066952  js      loc_180066A9B
0x180066958  mov     rax, [rdi]
0x18006695b  lea     r8, [rbp+var_30]
0x18006695f  mov     rdx, rsi
0x180066962  mov     rcx, rdi
0x180066965  mov     rax, [rax+20h]
0x180066969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006696e  mov     ebx, eax
0x180066970  test    eax, eax
0x180066972  js      loc_180066A9B
0x180066978  mov     rax, [rdi]
0x18006697b  lea     r8, [rbp+var_20]
0x18006697f  mov     rdx, [r14+68h]
0x180066983  mov     rcx, rdi
0x180066986  mov     rax, [rax+28h]
0x18006698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006698f  mov     ebx, eax
0x180066991  test    eax, eax
0x180066993  js      loc_180066A9B
0x180066999  mov     ecx, 78h ; 'x'; unsigned __int64
0x18006699e  mov     ebx, 8007000Eh
0x1800669a3  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800669a8  test    rax, rax
0x1800669ab  jz      loc_180066A9B
0x1800669b1  mov     rdx, [r14+1A8h]; struct IdParameters *
0x1800669b8  mov     rcx, rax; this
0x1800669bb  call    ??0CSyncChangeUnitWrapper@@QEAA@PEAVIdParameters@@@Z; CSyncChangeUnitWrapper::CSyncChangeUnitWrapper(IdParameters *)
0x1800669c0  mov     rdi, rax
0x1800669c3  test    rax, rax
0x1800669c6  jz      loc_180066A9B
0x1800669cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669d3  lea     rdx, WPP_GLOBAL_Control
0x1800669da  cmp     rcx, rdx
0x1800669dd  jz      short loc_180066A15
0x1800669df  test    byte ptr [rcx+1Ch], 8
0x1800669e3  jz      short loc_180066A15
0x1800669e5  cmp     byte ptr [rcx+19h], 5
0x1800669e9  jb      short loc_180066A15
0x1800669eb  mov     rcx, [rcx+10h]
0x1800669ef  lea     r9, aCsyncchangeuni_20; "CSyncChangeUnitWrapper::Init"
0x1800669f6  mov     edx, 0Fh
0x1800669fb  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180066a02  call    WPP_SF_s
0x180066a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a0e  lea     rdx, WPP_GLOBAL_Control
0x180066a15  mov     ebx, 80004003h
0x180066a1a  test    rsi, rsi
0x180066a1d  jz      short loc_180066A4A
0x180066a1f  lea     rax, [rdi+18h]
0x180066a23  test    rax, rax
0x180066a26  jz      short loc_180066A4A
0x180066a28  lock inc dword ptr [rsi-4]
0x180066a2c  mov     [rax], rsi
0x180066a2f  movups  xmm0, [rbp+var_20]
0x180066a33  mov     [rdi+68h], r14
0x180066a37  movdqu  xmmword ptr [rdi+20h], xmm0
0x180066a3c  lock inc dword ptr [r14+3Ch]
0x180066a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a48  xor     ebx, ebx
0x180066a4a  cmp     rcx, rdx
0x180066a4d  jz      short loc_180066A7B
0x180066a4f  test    byte ptr [rcx+1Ch], 8
0x180066a53  jz      short loc_180066A7B
0x180066a55  cmp     byte ptr [rcx+19h], 5
0x180066a59  jb      short loc_180066A7B
0x180066a5b  mov     rcx, [rcx+10h]
0x180066a5f  lea     r9, aCsyncchangeuni_20; "CSyncChangeUnitWrapper::Init"
0x180066a66  mov     edx, 10h
0x180066a6b  mov     [rsp+60h+var_40], ebx
0x180066a6f  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180066a76  call    WPP_SF_sD
0x180066a7b  test    ebx, ebx
0x180066a7d  js      short loc_180066A8C
0x180066a7f  mov     rdx, rdi; struct CSyncChangeUnitWrapper *
0x180066a82  mov     rcx, r14; this
0x180066a85  call    ?AddChangeUnit@CSyncChangeWrapper@@QEAAJPEAVCSyncChangeUnitWrapper@@@Z; CSyncChangeWrapper::AddChangeUnit(CSyncChangeUnitWrapper *)
0x180066a8a  mov     ebx, eax
0x180066a8c  mov     rax, [rdi]
0x180066a8f  mov     rcx, rdi
0x180066a92  mov     rax, [rax+10h]
0x180066a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a9b  mov     rcx, rsi; unsigned __int8 *
0x180066a9e  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180066aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180066aaa  lea     rax, WPP_GLOBAL_Control
0x180066ab1  cmp     rcx, rax
0x180066ab4  jz      short loc_180066AE2
0x180066ab6  test    byte ptr [rcx+1Ch], 8
0x180066aba  jz      short loc_180066AE2
0x180066abc  cmp     byte ptr [rcx+19h], 5
0x180066ac0  jb      short loc_180066AE2
0x180066ac2  mov     rcx, [rcx+10h]
0x180066ac6  lea     r9, aCsyncchangewra_86; "CSyncChangeWrapper::AddChangeUnitCopy"
0x180066acd  mov     edx, 9Ah
0x180066ad2  mov     [rsp+60h+var_40], ebx
0x180066ad6  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180066add  call    WPP_SF_sD
0x180066ae2  mov     eax, ebx
0x180066ae4  mov     rcx, [rbp+var_10]
0x180066ae8  xor     rcx, rsp; StackCookie
0x180066aeb  call    __security_check_cookie
0x180066af0  lea     r11, [rsp+60h+var_s0]
0x180066af5  mov     rbx, [r11+30h]
0x180066af9  mov     rsi, [r11+38h]
0x180066afd  mov     rsp, r11
0x180066b00  pop     r14
0x180066b02  pop     rdi
0x180066b03  pop     rbp
0x180066b04  retn
0x180066b05  test    eax, eax
0x180066b07  js      short loc_180066A9B
0x180066b09  mov     ebx, 8004101Dh
0x180066b0e  jmp     short loc_180066A9B
```

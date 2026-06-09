# CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)

- ea: `0x1800286b0`
- end: `0x18002895d`
- name: `?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z`
- size: `685`
- prototype: `void __fastcall(CServiceModule *this, char, unsigned int, int)`
- caller_count: `7`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000f428`
- `0x180012c70`
- `0x180023bd0`
- `0x180023e6c`
- `0x180023f54`
- `0x180024260`
- `0x180028964`

## callees

- `0x180001ec0`
- `0x180014124`
- `0x180015630`
- `0x1800286b0`
- `0x18002b3a8`
- `0x18002d13c`
- `0x18002d43c`
- `0x18002fb34`
- `0x18002fb4c`
- `0x180031010`

## string_xrefs

- `0x1800286ed`: `PENSERVICE_CServiceModule::_RemovePenProcessesWorker`
- `0x18002892d`: `PENSERVICE_CServiceModule::_RemovePenProcessesWorker`

## pseudocode

```c
void __fastcall CServiceModule::_RemovePenProcessesWorker(CServiceModule *this, char a2, unsigned int a3, int a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edx
  char v12; // cl
  int v13; // r11d
  int v14; // r13d
  __int64 v15; // rsi
  int v16; // r14d
  char v17; // bp
  _QWORD *v18; // rdi
  int v19; // r10d
  unsigned int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // ecx
  int v24; // [rsp+30h] [rbp-48h]
  int v25; // [rsp+34h] [rbp-44h]
  int v26; // [rsp+38h] [rbp-40h]
  int v27; // [rsp+80h] [rbp+8h]
  int v28; // [rsp+88h] [rbp+10h] BYREF
  char v29; // [rsp+90h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      50,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_RemovePenProcessesWorker");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v28 = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v8,
      (int)&byte_18003A19F,
      v9,
      v10,
      (__int64)&v28);
  }
  if ( *((_DWORD *)this + 95) )
  {
    v26 = a3 & 0x10;
    v11 = a3 & 4;
    v25 = a3 & 0x20;
    v12 = a3 & 1;
    v27 = v11;
    LOBYTE(v28) = a3 & 1;
    v13 = a3 & 2;
    v29 = a2 & 1;
    v14 = a2 & 2;
    v24 = (unsigned __int8)v13;
    v15 = 0;
    v16 = (a3 >> 3) & 1;
    do
    {
      v17 = 0;
      v18 = *(_QWORD **)(*((_QWORD *)this + 46) + 8 * v15);
      v19 = *((_DWORD *)v18 + 8);
      if ( v12 )
      {
        v20 = *((_DWORD *)this + 71);
        if ( v20 )
        {
          v21 = 0;
          while ( 1 )
          {
            v22 = *(_QWORD *)(*((_QWORD *)this + 34) + 8 * v21);
            if ( *(_DWORD *)(v22 + 4) == v19 )
              break;
            v21 = (unsigned int)(v21 + 1);
            if ( (unsigned int)v21 >= v20 )
              goto LABEL_16;
          }
          v17 = *(_BYTE *)(v22 + 8);
LABEL_16:
          v11 = v27;
        }
      }
      if ( v16 != (v19 == a4) )
        goto LABEL_38;
      if ( v11 )
      {
        if ( wcscmp_0((const wchar_t *)v18 + 279, L"Default") )
          goto LABEL_38;
        v13 = v24;
      }
      if ( (!(_BYTE)v28 || !*(_DWORD *)(*v18 + 12LL) && (!v17 || v13))
        && (!v25 || ((*(_DWORD *)(*v18 + 8LL) - 2) & 0xFFFFFFFD) == 0)
        && (!v26 || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 56LL))(*v18)) )
      {
        if ( v29 && *((_DWORD *)v18 + 270) == 1 )
          CPenProcess::Stop((CPenProcess *)v18);
        if ( v14 )
          CPenProcess::Relinquish((CPenProcess *)v18);
        if ( *((_DWORD *)v18 + 270) != 1 )
        {
          v23 = *((_DWORD *)this + 95);
          if ( (unsigned int)v15 < v23 - 1 )
            memcpy_0(
              (void *)(*((_QWORD *)this + 46) + 8 * v15),
              (const void *)(*((_QWORD *)this + 46) + 8LL * (unsigned int)(v15 + 1)),
              (unsigned int)(8 * (v23 - v15) - 8));
          --*((_DWORD *)this + 95);
          CPenProcess::Release((CPenProcess *)v18);
          goto LABEL_39;
        }
      }
LABEL_38:
      v15 = (unsigned int)(v15 + 1);
LABEL_39:
      v12 = v28;
      v13 = v24;
      v11 = v27;
    }
    while ( (unsigned int)v15 < *((_DWORD *)this + 95) );
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      51,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_RemovePenProcessesWorker");
}

```

## disassembly

```asm
0x1800286b0  mov     [rsp+arg_18], rbx
0x1800286b5  push    rbp
0x1800286b6  push    rsi
0x1800286b7  push    rdi
0x1800286b8  push    r12
0x1800286ba  push    r13
0x1800286bc  push    r14
0x1800286be  push    r15
0x1800286c0  sub     rsp, 40h
0x1800286c4  mov     r15d, r9d
0x1800286c7  mov     r14d, r8d
0x1800286ca  mov     r13d, edx
0x1800286cd  mov     rbx, rcx
0x1800286d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286d7  lea     rax, WPP_GLOBAL_Control
0x1800286de  cmp     rcx, rax
0x1800286e1  jz      short loc_180028705
0x1800286e3  test    byte ptr [rcx+1Ch], 10h
0x1800286e7  jz      short loc_180028705
0x1800286e9  mov     rcx, [rcx+10h]
0x1800286ed  lea     r9, aPenserviceCser_28; "PENSERVICE_CServiceModule::_RemovePenPr"...
0x1800286f4  mov     edx, 32h ; '2'
0x1800286f9  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180028700  call    WPP_SF_s
0x180028705  mov     eax, cs:dword_1800411A8
0x18002870b  cmp     eax, 5
0x18002870e  jbe     short loc_180028746
0x180028710  mov     edx, 4000000h
0x180028715  lea     rcx, dword_1800411A8
0x18002871c  call    _tlgKeywordOn
0x180028721  test    al, al
0x180028723  jz      short loc_180028746
0x180028725  lea     rax, [rsp+78h+arg_8]
0x18002872d  mov     [rsp+78h+arg_8], r15d
0x180028735  lea     rdx, byte_18003A19F
0x18002873c  mov     [rsp+78h+var_58], rax
0x180028741  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180028746  cmp     dword ptr [rbx+17Ch], 0
0x18002874d  jbe     loc_180028910
0x180028753  mov     eax, r14d
0x180028756  mov     edx, r14d
0x180028759  and     eax, 10h
0x18002875c  mov     cl, r14b
0x18002875f  mov     [rsp+78h+var_40], eax
0x180028763  mov     r11d, r14d
0x180028766  mov     eax, r14d
0x180028769  and     edx, 4
0x18002876c  and     eax, 20h
0x18002876f  shr     r14d, 3
0x180028773  mov     [rsp+78h+var_44], eax
0x180028777  and     cl, 1
0x18002877a  mov     al, r13b
0x18002877d  mov     [rsp+78h+arg_0], edx
0x180028784  and     al, 1
0x180028786  mov     byte ptr [rsp+78h+arg_8], cl
0x18002878d  and     r11d, 2
0x180028791  mov     [rsp+78h+arg_10], al
0x180028798  and     r13d, 2
0x18002879c  mov     [rsp+78h+var_48], r11d
0x1800287a1  xor     esi, esi
0x1800287a3  and     r14d, 1
0x1800287a7  mov     rax, [rbx+170h]
0x1800287ae  xor     bpl, bpl
0x1800287b1  mov     rdi, [rax+rsi*8]
0x1800287b5  mov     r10d, [rdi+20h]
0x1800287b9  test    cl, cl
0x1800287bb  jz      short loc_1800287F0
0x1800287bd  mov     r8d, [rbx+11Ch]
0x1800287c4  test    r8d, r8d
0x1800287c7  jz      short loc_1800287F0
0x1800287c9  mov     r9, [rbx+110h]
0x1800287d0  xor     ecx, ecx
0x1800287d2  mov     rax, [r9+rcx*8]
0x1800287d6  cmp     [rax+4], r10d
0x1800287da  jz      short loc_1800287E5
0x1800287dc  inc     ecx
0x1800287de  cmp     ecx, r8d
0x1800287e1  jb      short loc_1800287D2
0x1800287e3  jmp     short loc_1800287E9
0x1800287e5  mov     bpl, [rax+8]
0x1800287e9  mov     edx, [rsp+78h+arg_0]
0x1800287f0  xor     eax, eax
0x1800287f2  cmp     r10d, r15d
0x1800287f5  setz    al
0x1800287f8  cmp     r14d, eax
0x1800287fb  jnz     loc_1800288EF
0x180028801  test    edx, edx
0x180028803  jz      short loc_180028825
0x180028805  lea     rcx, [rdi+22Eh]; String1
0x18002880c  lea     rdx, aDefault; "Default"
0x180028813  call    wcscmp_0
0x180028818  test    eax, eax
0x18002881a  jnz     loc_1800288EF
0x180028820  mov     r11d, [rsp+78h+var_48]
0x180028825  cmp     byte ptr [rsp+78h+arg_8], 0
0x18002882d  jz      short loc_18002884A
0x18002882f  mov     rax, [rdi]
0x180028832  cmp     dword ptr [rax+0Ch], 0
0x180028836  jnz     loc_1800288EF
0x18002883c  test    bpl, bpl
0x18002883f  jz      short loc_18002884A
0x180028841  test    r11d, r11d
0x180028844  jz      loc_1800288EF
0x18002884a  cmp     [rsp+78h+var_44], 0
0x18002884f  jz      short loc_180028866
0x180028851  mov     rax, [rdi]
0x180028854  mov     ecx, [rax+8]
0x180028857  sub     ecx, 2
0x18002885a  test    ecx, 0FFFFFFFDh
0x180028860  jnz     loc_1800288EF
0x180028866  cmp     [rsp+78h+var_40], 0
0x18002886b  jz      short loc_180028880
0x18002886d  mov     rcx, [rdi]
0x180028870  mov     rax, [rcx]
0x180028873  mov     rax, [rax+38h]
0x180028877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002887c  test    eax, eax
0x18002887e  jz      short loc_1800288EF
0x180028880  cmp     [rsp+78h+arg_10], 0
0x180028888  jz      short loc_18002889B
0x18002888a  cmp     dword ptr [rdi+438h], 1
0x180028891  jnz     short loc_18002889B
0x180028893  mov     rcx, rdi; this
0x180028896  call    ?Stop@CPenProcess@@QEAAHXZ; CPenProcess::Stop(void)
0x18002889b  test    r13d, r13d
0x18002889e  jz      short loc_1800288A8
0x1800288a0  mov     rcx, rdi; this
0x1800288a3  call    ?Relinquish@CPenProcess@@QEAAHXZ; CPenProcess::Relinquish(void)
0x1800288a8  cmp     dword ptr [rdi+438h], 1
0x1800288af  jz      short loc_1800288EF
0x1800288b1  mov     ecx, [rbx+17Ch]
0x1800288b7  lea     eax, [rcx-1]
0x1800288ba  cmp     esi, eax
0x1800288bc  jnb     short loc_1800288DF
0x1800288be  mov     r9, [rbx+170h]
0x1800288c5  lea     eax, [rsi+1]
0x1800288c8  sub     ecx, esi
0x1800288ca  lea     rdx, [r9+rax*8]; Src
0x1800288ce  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[rcx*8]; Size
0x1800288d6  lea     rcx, [r9+rsi*8]; void *
0x1800288da  call    memcpy_0
0x1800288df  dec     dword ptr [rbx+17Ch]
0x1800288e5  mov     rcx, rdi; this
0x1800288e8  call    ?Release@CPenProcess@@QEAAKXZ; CPenProcess::Release(void)
0x1800288ed  jmp     short loc_1800288F1
0x1800288ef  inc     esi
0x1800288f1  mov     cl, byte ptr [rsp+78h+arg_8]
0x1800288f8  mov     r11d, [rsp+78h+var_48]
0x1800288fd  mov     edx, [rsp+78h+arg_0]
0x180028904  cmp     esi, [rbx+17Ch]
0x18002890a  jb      loc_1800287A7
0x180028910  mov     rcx, cs:WPP_GLOBAL_Control
0x180028917  lea     rax, WPP_GLOBAL_Control
0x18002891e  cmp     rcx, rax
0x180028921  jz      short loc_180028945
0x180028923  test    byte ptr [rcx+1Ch], 10h
0x180028927  jz      short loc_180028945
0x180028929  mov     rcx, [rcx+10h]
0x18002892d  lea     r9, aPenserviceCser_28; "PENSERVICE_CServiceModule::_RemovePenPr"...
0x180028934  mov     edx, 33h ; '3'
0x180028939  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180028940  call    WPP_SF_s
0x180028945  mov     rbx, [rsp+78h+arg_18]
0x18002894d  add     rsp, 40h
0x180028951  pop     r15
0x180028953  pop     r14
0x180028955  pop     r13
0x180028957  pop     r12
0x180028959  pop     rdi
0x18002895a  pop     rsi
0x18002895b  pop     rbp
0x18002895c  retn
```

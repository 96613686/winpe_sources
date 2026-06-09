# CServiceModule::CreatePenSession(ulong)

- ea: `0x1800142b0`
- end: `0x180014412`
- name: `?CreatePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z`
- size: `354`
- prototype: `struct CPenSession *__fastcall(CServiceModule *this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800141d4`

## callees

- `0x180001ec0`
- `0x1800142b0`
- `0x180015630`
- `0x18001bc20`
- `0x18001f484`
- `0x18001fd50`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x1800142e4`: `PENSERVICE_CServiceModule::CreatePenSession`
- `0x1800143e4`: `PENSERVICE_CServiceModule::CreatePenSession`

## pseudocode

```c
struct CPenSession *__fastcall CServiceModule::CreatePenSession(CServiceModule *this, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  CPenSession *v7; // rax
  unsigned int v8; // edx
  CPenSession *v9; // rbx
  char *v10; // rdi
  unsigned int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rax
  CPenSession *v15; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      32,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::CreatePenSession",
      a2);
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    LODWORD(v15) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (int)&dword_180039AB4,
      v5,
      v6,
      (__int64)&v15);
  }
  v7 = (CPenSession *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v7;
  v9 = v7;
  if ( !v7 )
    goto LABEL_12;
  *(_DWORD *)v7 = 1;
  *((_DWORD *)v7 + 1) = a2;
  *((_WORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 8) = 0;
  *((_QWORD *)v7 + 9) = 0;
  *((_QWORD *)v7 + 10) = 0;
  *((_QWORD *)v7 + 11) = 0;
  v10 = (char *)this + 192;
  v11 = *((_DWORD *)this + 71);
  v12 = v11 + 1;
  if ( v11 + 1 < v11 || (int)CPbPreallocArray<CPenProcess *,10>::EnsureSize(v10) < 0 )
  {
    CPenSession::`scalar deleting destructor'(v9, v8);
LABEL_12:
    v9 = 0;
    goto LABEL_13;
  }
  v13 = *((_QWORD *)v10 + 10);
  *((_DWORD *)v10 + 23) = v12;
  *(_QWORD *)(v13 + 8LL * (v12 - 1)) = v9;
LABEL_13:
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      33,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::CreatePenSession");
  return v9;
}

```

## disassembly

```asm
0x1800142b0  mov     [rsp+arg_0], rbx
0x1800142b5  mov     [rsp+arg_8], rbp
0x1800142ba  push    rsi
0x1800142bb  push    rdi
0x1800142bc  push    r14
0x1800142be  sub     rsp, 30h
0x1800142c2  mov     edi, edx
0x1800142c4  mov     rsi, rcx
0x1800142c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142ce  lea     r14, WPP_GLOBAL_Control
0x1800142d5  cmp     rcx, r14
0x1800142d8  jz      short loc_180014300
0x1800142da  test    byte ptr [rcx+1Ch], 10h
0x1800142de  jz      short loc_180014300
0x1800142e0  mov     rcx, [rcx+10h]
0x1800142e4  lea     r9, aPenserviceCser_29; "PENSERVICE_CServiceModule::CreatePenSes"...
0x1800142eb  mov     edx, 20h ; ' '
0x1800142f0  mov     dword ptr [rsp+48h+var_28], edi
0x1800142f4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800142fb  call    WPP_SF_sd
0x180014300  mov     eax, cs:dword_1800411A8
0x180014306  xor     ebp, ebp
0x180014308  cmp     eax, 5
0x18001430b  jbe     short loc_18001433C
0x18001430d  mov     edx, 4000000h
0x180014312  lea     rcx, dword_1800411A8
0x180014319  call    _tlgKeywordOn
0x18001431e  test    al, al
0x180014320  jz      short loc_18001433C
0x180014322  lea     rax, [rsp+48h+arg_10]
0x180014327  mov     dword ptr [rsp+48h+arg_10], edi
0x18001432b  lea     rdx, dword_180039AB4
0x180014332  mov     [rsp+48h+var_28], rax
0x180014337  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001433c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014343  mov     ecx, 60h ; '`'; unsigned __int64
0x180014348  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001434d  mov     [rsp+48h+arg_10], rax
0x180014352  mov     rbx, rax
0x180014355  test    rax, rax
0x180014358  jz      short loc_1800143CB
0x18001435a  mov     dword ptr [rax], 1
0x180014360  mov     [rax+4], edi
0x180014363  mov     [rax+8], bp
0x180014367  mov     [rax+10h], rbp
0x18001436b  mov     [rax+18h], rbp
0x18001436f  mov     [rax+20h], rbp
0x180014373  mov     [rax+28h], rbp
0x180014377  mov     [rax+30h], rbp
0x18001437b  mov     [rax+38h], rbp
0x18001437f  mov     [rax+40h], rbp
0x180014383  mov     [rax+48h], rbp
0x180014387  mov     [rax+50h], rbp
0x18001438b  mov     [rax+58h], rbp
0x18001438f  test    rax, rax
0x180014392  jz      short loc_1800143CE
0x180014394  lea     rdi, [rsi+0C0h]
0x18001439b  mov     eax, [rdi+5Ch]
0x18001439e  lea     esi, [rax+1]
0x1800143a1  cmp     esi, eax
0x1800143a3  jb      short loc_1800143C3
0x1800143a5  mov     edx, esi
0x1800143a7  mov     rcx, rdi; Src
0x1800143aa  call    ?EnsureSize@?$CPbPreallocArray@PEAVCPenProcess@@$09@@IEAAJIH@Z; CPbPreallocArray<CPenProcess *,10>::EnsureSize(uint,int)
0x1800143af  test    eax, eax
0x1800143b1  js      short loc_1800143C3
0x1800143b3  mov     rax, [rdi+50h]
0x1800143b7  lea     ecx, [rsi-1]
0x1800143ba  mov     [rdi+5Ch], esi
0x1800143bd  mov     [rax+rcx*8], rbx
0x1800143c1  jmp     short loc_1800143CE
0x1800143c3  mov     rcx, rbx; this
0x1800143c6  call    ??_GCPenSession@@QEAAPEAXI@Z; CPenSession::`scalar deleting destructor'(uint)
0x1800143cb  mov     rbx, rbp
0x1800143ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d5  cmp     rcx, r14
0x1800143d8  jz      short loc_1800143FC
0x1800143da  test    byte ptr [rcx+1Ch], 10h
0x1800143de  jz      short loc_1800143FC
0x1800143e0  mov     rcx, [rcx+10h]
0x1800143e4  lea     r9, aPenserviceCser_29; "PENSERVICE_CServiceModule::CreatePenSes"...
0x1800143eb  mov     edx, 21h ; '!'
0x1800143f0  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800143f7  call    WPP_SF_s
0x1800143fc  mov     rbp, [rsp+48h+arg_8]
0x180014401  mov     rax, rbx
0x180014404  mov     rbx, [rsp+48h+arg_0]
0x180014409  add     rsp, 30h
0x18001440d  pop     r14
0x18001440f  pop     rdi
0x180014410  pop     rsi
0x180014411  retn
```

# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003501c`
- end: `0x1800351f2`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002ea38`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000ea20`
- `0x18003501c`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035145`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800351a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035145`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800351a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800350a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800351c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800350a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800351c4`

## string_xrefs

- `0x18003508b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x180035123`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int *v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v17 = &v18;
  v6 = (int)a4;
  v19 = 0;
  LOBYTE(v18) = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v19, a1, L"PackageExternalLocation\\Data");
  if ( v7 < 0 )
  {
    v8 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      (int)&v18);
LABEL_4:
    v9 = v19;
    v19 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v7;
  }
  if ( !(_BYTE)v18 )
  {
    v7 = -2140733422;
    v8 = 251;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v7 < 0 )
  {
    v11 = 254;
    goto LABEL_11;
  }
  LODWORD(v17) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v24);
  if ( v7 < 0 )
  {
    v11 = 255;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         L"PackageExternalLocation\\Data");
  if ( v7 < 0 )
  {
    v11 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v7,
      (int)v17);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13, v12);
    goto LABEL_4;
  }
  v15 = v20;
  v20 = 0;
  if ( v15 )
    SRCache_Free(v15, v14);
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18003501c  push    rbp
0x18003501e  push    rbx
0x18003501f  push    rsi
0x180035020  push    rdi
0x180035021  push    r14
0x180035023  push    r15
0x180035025  lea     rbp, [rsp-178h]
0x18003502d  sub     rsp, 278h
0x180035034  mov     rax, cs:__security_cookie
0x18003503b  xor     rax, rsp
0x18003503e  mov     [rbp+1A0h+var_40], rax
0x180035045  mov     r14, rdx
0x180035048  lea     rax, [rsp+2A0h+var_270]
0x18003504d  mov     rdx, rcx
0x180035050  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180035055  mov     rdi, r8
0x180035058  lea     rcx, [rsp+2A0h+var_268]
0x18003505d  xor     r15d, r15d
0x180035060  lea     r8, aPackageexterna; "PackageExternalLocation\\Data"
0x180035067  mov     rsi, r9
0x18003506a  mov     [rsp+2A0h+var_268], r15
0x18003506f  mov     byte ptr [rsp+2A0h+var_270], r15b
0x180035074  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035079  mov     ebx, eax
0x18003507b  test    eax, eax
0x18003507d  jns     short loc_1800350BC
0x18003507f  mov     edx, 0FAh; void *
0x180035084  mov     rcx, [rbp+1A8h]; this
0x18003508b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035092  mov     r9d, ebx; char *
0x180035095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003509a  mov     rcx, [rsp+2A0h+var_268]
0x18003509f  mov     [rsp+2A0h+var_268], r15
0x1800350a4  test    rcx, rcx
0x1800350a7  jz      short loc_1800350B5
0x1800350a9  call    cs:__imp_SRCacheContext_Close
0x1800350b0  nop     dword ptr [rax+rax+00h]
0x1800350b5  mov     eax, ebx
0x1800350b7  jmp     loc_1800351D2
0x1800350bc  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x1800350c1  jnz     short loc_1800350CF
0x1800350c3  mov     ebx, 80670012h
0x1800350c8  mov     edx, 0FBh
0x1800350cd  jmp     short loc_180035084
0x1800350cf  xor     edx, edx; Val
0x1800350d1  mov     [rsp+2A0h+var_260], r15
0x1800350d6  mov     r8d, 200h; Size
0x1800350dc  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800350e1  call    memset_0
0x1800350e6  lea     rax, [rsp+2A0h+var_258]
0x1800350eb  mov     [rbp+1A0h+var_58], r15
0x1800350f2  mov     rdx, r14; unsigned __int64
0x1800350f5  mov     [rbp+1A0h+var_48], rax
0x1800350fc  lea     rcx, [rsp+2A0h+var_260]; this
0x180035101  mov     [rbp+1A0h+var_50], 100h
0x18003510c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180035111  mov     ebx, eax
0x180035113  test    eax, eax
0x180035115  jns     short loc_180035156
0x180035117  mov     edx, 0FEh; void *
0x18003511c  mov     rcx, [rbp+1A8h]; this
0x180035123  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003512a  mov     r9d, ebx; char *
0x18003512d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035132  mov     rcx, [rsp+2A0h+var_260]
0x180035137  mov     [rsp+2A0h+var_260], r15
0x18003513c  test    rcx, rcx
0x18003513f  jz      loc_18003509A
0x180035145  call    cs:__imp_SRCache_Free
0x18003514c  nop     dword ptr [rax+rax+00h]
0x180035151  jmp     loc_18003509A
0x180035156  mov     r8, [rbp+1A0h+var_48]
0x18003515d  lea     rdx, [rsp+2A0h+var_268]
0x180035162  mov     rcx, rdi
0x180035165  mov     qword ptr [rsp+2A0h+var_280], rsi
0x18003516a  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18003516f  mov     ebx, eax
0x180035171  test    eax, eax
0x180035173  jns     short loc_18003517C
0x180035175  mov     edx, 0FFh
0x18003517a  jmp     short loc_18003511C
0x18003517c  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x180035183  lea     rcx, [rsp+2A0h+var_268]; this
0x180035188  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18003518d  mov     ebx, eax
0x18003518f  test    eax, eax
0x180035191  jns     short loc_18003519A
0x180035193  mov     edx, 101h
0x180035198  jmp     short loc_18003511C
0x18003519a  mov     rcx, [rsp+2A0h+var_260]
0x18003519f  mov     [rsp+2A0h+var_260], r15
0x1800351a4  test    rcx, rcx
0x1800351a7  jz      short loc_1800351B5
0x1800351a9  call    cs:__imp_SRCache_Free
0x1800351b0  nop     dword ptr [rax+rax+00h]
0x1800351b5  mov     rcx, [rsp+2A0h+var_268]
0x1800351ba  mov     [rsp+2A0h+var_268], r15
0x1800351bf  test    rcx, rcx
0x1800351c2  jz      short loc_1800351D0
0x1800351c4  call    cs:__imp_SRCacheContext_Close
0x1800351cb  nop     dword ptr [rax+rax+00h]
0x1800351d0  xor     eax, eax
0x1800351d2  mov     rcx, [rbp+1A0h+var_40]
0x1800351d9  xor     rcx, rsp; StackCookie
0x1800351dc  call    __security_check_cookie
0x1800351e1  add     rsp, 278h
0x1800351e8  pop     r15
0x1800351ea  pop     r14
0x1800351ec  pop     rdi
0x1800351ed  pop     rsi
0x1800351ee  pop     rbx
0x1800351ef  pop     rbp
0x1800351f0  retn
```

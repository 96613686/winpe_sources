# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800350cc`
- end: `0x1800352a2`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d418`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x1800350cc`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035159`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035274`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035159`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035274`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800351f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035259`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800351f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035259`

## string_xrefs

- `0x18003513b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x1800351d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x1800350cc  push    rbp
0x1800350ce  push    rbx
0x1800350cf  push    rsi
0x1800350d0  push    rdi
0x1800350d1  push    r14
0x1800350d3  push    r15
0x1800350d5  lea     rbp, [rsp-178h]
0x1800350dd  sub     rsp, 278h
0x1800350e4  mov     rax, cs:__security_cookie
0x1800350eb  xor     rax, rsp
0x1800350ee  mov     [rbp+1A0h+var_40], rax
0x1800350f5  mov     r14, rdx
0x1800350f8  lea     rax, [rsp+2A0h+var_270]
0x1800350fd  mov     rdx, rcx
0x180035100  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180035105  mov     rdi, r8
0x180035108  lea     rcx, [rsp+2A0h+var_268]
0x18003510d  xor     r15d, r15d
0x180035110  lea     r8, aPackageexterna; "PackageExternalLocation\\Data"
0x180035117  mov     rsi, r9
0x18003511a  mov     [rsp+2A0h+var_268], r15
0x18003511f  mov     byte ptr [rsp+2A0h+var_270], r15b
0x180035124  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035129  mov     ebx, eax
0x18003512b  test    eax, eax
0x18003512d  jns     short loc_18003516C
0x18003512f  mov     edx, 0FAh; void *
0x180035134  mov     rcx, [rbp+1A8h]; this
0x18003513b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035142  mov     r9d, ebx; char *
0x180035145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003514a  mov     rcx, [rsp+2A0h+var_268]
0x18003514f  mov     [rsp+2A0h+var_268], r15
0x180035154  test    rcx, rcx
0x180035157  jz      short loc_180035165
0x180035159  call    cs:__imp_SRCacheContext_Close
0x180035160  nop     dword ptr [rax+rax+00h]
0x180035165  mov     eax, ebx
0x180035167  jmp     loc_180035282
0x18003516c  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x180035171  jnz     short loc_18003517F
0x180035173  mov     ebx, 80670012h
0x180035178  mov     edx, 0FBh
0x18003517d  jmp     short loc_180035134
0x18003517f  xor     edx, edx; Val
0x180035181  mov     [rsp+2A0h+var_260], r15
0x180035186  mov     r8d, 200h; Size
0x18003518c  lea     rcx, [rsp+2A0h+var_258]; void *
0x180035191  call    memset_0
0x180035196  lea     rax, [rsp+2A0h+var_258]
0x18003519b  mov     [rbp+1A0h+var_58], r15
0x1800351a2  mov     rdx, r14; unsigned __int64
0x1800351a5  mov     [rbp+1A0h+var_48], rax
0x1800351ac  lea     rcx, [rsp+2A0h+var_260]; this
0x1800351b1  mov     [rbp+1A0h+var_50], 100h
0x1800351bc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800351c1  mov     ebx, eax
0x1800351c3  test    eax, eax
0x1800351c5  jns     short loc_180035206
0x1800351c7  mov     edx, 0FEh; void *
0x1800351cc  mov     rcx, [rbp+1A8h]; this
0x1800351d3  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800351da  mov     r9d, ebx; char *
0x1800351dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800351e2  mov     rcx, [rsp+2A0h+var_260]
0x1800351e7  mov     [rsp+2A0h+var_260], r15
0x1800351ec  test    rcx, rcx
0x1800351ef  jz      loc_18003514A
0x1800351f5  call    cs:__imp_SRCache_Free
0x1800351fc  nop     dword ptr [rax+rax+00h]
0x180035201  jmp     loc_18003514A
0x180035206  mov     r8, [rbp+1A0h+var_48]
0x18003520d  lea     rdx, [rsp+2A0h+var_268]
0x180035212  mov     rcx, rdi
0x180035215  mov     qword ptr [rsp+2A0h+var_280], rsi
0x18003521a  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18003521f  mov     ebx, eax
0x180035221  test    eax, eax
0x180035223  jns     short loc_18003522C
0x180035225  mov     edx, 0FFh
0x18003522a  jmp     short loc_1800351CC
0x18003522c  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x180035233  lea     rcx, [rsp+2A0h+var_268]; this
0x180035238  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18003523d  mov     ebx, eax
0x18003523f  test    eax, eax
0x180035241  jns     short loc_18003524A
0x180035243  mov     edx, 101h
0x180035248  jmp     short loc_1800351CC
0x18003524a  mov     rcx, [rsp+2A0h+var_260]
0x18003524f  mov     [rsp+2A0h+var_260], r15
0x180035254  test    rcx, rcx
0x180035257  jz      short loc_180035265
0x180035259  call    cs:__imp_SRCache_Free
0x180035260  nop     dword ptr [rax+rax+00h]
0x180035265  mov     rcx, [rsp+2A0h+var_268]
0x18003526a  mov     [rsp+2A0h+var_268], r15
0x18003526f  test    rcx, rcx
0x180035272  jz      short loc_180035280
0x180035274  call    cs:__imp_SRCacheContext_Close
0x18003527b  nop     dword ptr [rax+rax+00h]
0x180035280  xor     eax, eax
0x180035282  mov     rcx, [rbp+1A0h+var_40]
0x180035289  xor     rcx, rsp; StackCookie
0x18003528c  call    __security_check_cookie
0x180035291  add     rsp, 278h
0x180035298  pop     r15
0x18003529a  pop     r14
0x18003529c  pop     rdi
0x18003529d  pop     rsi
0x18003529e  pop     rbx
0x18003529f  pop     rbp
0x1800352a0  retn
```

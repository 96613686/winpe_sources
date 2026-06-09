# ConfigLocationRootNode::InitializeDescendents(ConfigLocationsTree *)

- ea: `0x18000a104`
- end: `0x18000a1e4`
- name: `?InitializeDescendents@ConfigLocationRootNode@@AEAAXPEAVConfigLocationsTree@@@Z`
- size: `224`
- prototype: `void __fastcall(ConfigLocationRootNode *__hidden this, struct ConfigLocationsTree *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800098a0`

## callees

- `0x180007aac`
- `0x180009b44`
- `0x18000a104`
- `0x18000dcb0`
- `0x18000de58`
- `0x1800130a0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConfigLocationRootNode::InitializeDescendents(
        ConfigLocationRootNode *this,
        struct ConfigLocationsTree *a2)
{
  __int64 v4; // rax
  OLECHAR *v5; // rdx
  __int64 v6; // rax
  struct IUnknown *v7[3]; // [rsp+20h] [rbp-40h] BYREF
  __int16 v8; // [rsp+38h] [rbp-28h] BYREF
  char v9; // [rsp+3Ah] [rbp-26h]
  int v10; // [rsp+3Ch] [rbp-24h]
  __int16 *v11; // [rsp+40h] [rbp-20h]
  int v12; // [rsp+48h] [rbp-18h]
  struct IUnknown *v13; // [rsp+50h] [rbp-10h]

  LOWORD(v7[0]) = 0;
  v7[1] = 0;
  v7[2] = 0;
  v9 = 0;
  v10 = 2;
  v11 = &v8;
  v12 = 0;
  v8 = 0;
  v13 = 0;
  v4 = *((_QWORD *)a2 + 3);
  v5 = (OLECHAR *)&qword_1800181B0;
  if ( *((_QWORD *)a2 + 5) )
    v5 = (OLECHAR *)*((_QWORD *)a2 + 5);
  ConfigLocationsEnumerator::Reset(v7, v5, *(struct IAppHostAdminManager **)(v4 + 16));
  while ( ConfigLocationsEnumerator::MoveNext((ConfigLocationsEnumerator *)v7) )
  {
    v6 = (*(__int64 (__fastcall **)(ConfigLocationRootNode *, struct ConfigLocationsTree *, __int16 *))(*(_QWORD *)this + 104LL))(
           this,
           a2,
           v11);
    if ( *(struct IUnknown **)(v6 + 80) != v13 )
      ATL::AtlComPtrAssign((struct IUnknown **)(v6 + 80), v13);
  }
  ConfigLocationsEnumerator::~ConfigLocationsEnumerator((ConfigLocationsEnumerator *)v7);
}

```

## disassembly

```asm
0x18000a104  mov     [rsp-8+arg_10], rbx
0x18000a109  mov     [rsp-8+arg_18], rdi
0x18000a10e  push    rbp
0x18000a10f  mov     rbp, rsp
0x18000a112  sub     rsp, 60h
0x18000a116  mov     rax, cs:__security_cookie
0x18000a11d  xor     rax, rsp
0x18000a120  mov     [rbp+var_8], rax
0x18000a124  mov     rdi, rdx
0x18000a127  mov     rbx, rcx
0x18000a12a  mov     [rbp+var_40], 0
0x18000a130  mov     [rbp+var_38], 0
0x18000a138  mov     [rbp+var_30], 0
0x18000a140  mov     [rbp+var_26], 0
0x18000a144  mov     [rbp+var_24], 2
0x18000a14b  lea     rax, [rbp+var_28]
0x18000a14f  mov     [rbp+var_20], rax
0x18000a153  mov     [rbp+var_18], 0
0x18000a15a  xor     eax, eax
0x18000a15c  mov     [rbp+var_28], ax
0x18000a160  mov     [rbp+var_10], rax
0x18000a164  mov     rax, [rdx+18h]
0x18000a168  lea     rdx, qword_1800181B0
0x18000a16f  cmp     qword ptr [rdi+28h], 0
0x18000a174  cmovnz  rdx, [rdi+28h]; unsigned __int16 *
0x18000a179  mov     r8, [rax+10h]; struct IAppHostAdminManager *
0x18000a17d  lea     rcx, [rbp+var_40]; this
0x18000a181  call    ?Reset@ConfigLocationsEnumerator@@QEAAXPEBGPEAUIAppHostAdminManager@@@Z; ConfigLocationsEnumerator::Reset(ushort const *,IAppHostAdminManager *)
0x18000a186  jmp     short loc_18000A1B0
0x18000a188  mov     rax, [rbx]
0x18000a18b  mov     r8, [rbp+var_20]
0x18000a18f  mov     rdx, rdi
0x18000a192  mov     rcx, rbx
0x18000a195  mov     rax, [rax+68h]
0x18000a199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a19e  mov     rdx, [rbp+var_10]; struct IUnknown *
0x18000a1a2  lea     rcx, [rax+50h]; struct IUnknown **
0x18000a1a6  cmp     [rcx], rdx
0x18000a1a9  jz      short loc_18000A1B0
0x18000a1ab  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000a1b0  lea     rcx, [rbp+var_40]; this
0x18000a1b4  call    ?MoveNext@ConfigLocationsEnumerator@@QEAA_NXZ; ConfigLocationsEnumerator::MoveNext(void)
0x18000a1b9  test    al, al
0x18000a1bb  jnz     short loc_18000A188
0x18000a1bd  lea     rcx, [rbp+var_40]; this
0x18000a1c1  call    ??1ConfigLocationsEnumerator@@QEAA@XZ; ConfigLocationsEnumerator::~ConfigLocationsEnumerator(void)
0x18000a1c6  mov     rcx, [rbp+var_8]
0x18000a1ca  xor     rcx, rsp; StackCookie
0x18000a1cd  call    __security_check_cookie
0x18000a1d2  lea     r11, [rsp+60h+var_s0]
0x18000a1d7  mov     rbx, [r11+20h]
0x18000a1db  mov     rdi, [r11+28h]
0x18000a1df  mov     rsp, r11
0x18000a1e2  pop     rbp
0x18000a1e3  retn
```

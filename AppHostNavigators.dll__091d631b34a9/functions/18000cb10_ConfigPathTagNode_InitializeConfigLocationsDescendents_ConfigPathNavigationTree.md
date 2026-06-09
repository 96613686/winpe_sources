# ConfigPathTagNode::InitializeConfigLocationsDescendents(ConfigPathNavigationTree *)

- ea: `0x18000cb10`
- end: `0x18000cc3f`
- name: `?InitializeConfigLocationsDescendents@ConfigPathTagNode@@AEAAXPEAVConfigPathNavigationTree@@@Z`
- size: `303`
- prototype: `void __fastcall(ConfigPathTagNode *__hidden this, struct ConfigPathNavigationTree *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d920`

## callees

- `0x1800021e0`
- `0x180009b44`
- `0x18000c8a8`
- `0x18000c9bc`
- `0x18000cb10`
- `0x18000dcb0`
- `0x18000de58`
- `0x1800130a0`

## string_xrefs

- `0x18000cbd7`: `ConfigPathNodeType_Location`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConfigPathTagNode::InitializeConfigLocationsDescendents(
        ConfigPathTagNode *this,
        struct ConfigPathNavigationTree *a2)
{
  int v4; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v5; // [rsp+28h] [rbp-D8h]
  __int16 v6; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h]
  __int64 v8; // [rsp+40h] [rbp-C0h]
  __int16 v9; // [rsp+48h] [rbp-B8h] BYREF
  char v10; // [rsp+4Ah] [rbp-B6h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  __int16 *v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  _BYTE v15[4]; // [rsp+68h] [rbp-98h] BYREF
  int v16; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  __int16 v19; // [rsp+80h] [rbp-80h] BYREF

  v15[2] = 0;
  v16 = 520;
  v17 = (unsigned __int16 *)&v19;
  v18 = 0;
  v19 = 0;
  ConfigPathNode::GetConfigPath(this, a2, (struct STRU *)v15);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 2;
  v12 = &v9;
  v13 = 0;
  v9 = 0;
  v14 = 0;
  ConfigLocationsEnumerator::Reset(
    (ConfigLocationsEnumerator *)&v6,
    v17,
    *(struct IAppHostAdminManager **)(*((_QWORD *)a2 + 20) + 16LL));
  while ( ConfigLocationsEnumerator::MoveNext((ConfigLocationsEnumerator *)&v6) )
  {
    v4 = 10;
    v5 = L"ConfigPathNodeType_Location";
    ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(this, a2, v12, &v4);
  }
  ConfigLocationsEnumerator::~ConfigLocationsEnumerator((ConfigLocationsEnumerator *)&v6);
  BUFFER::~BUFFER((BUFFER *)v15);
}

```

## disassembly

```asm
0x18000cb10  mov     [rsp-8+arg_10], rbx
0x18000cb15  mov     [rsp-8+arg_18], rdi
0x18000cb1a  push    rbp
0x18000cb1b  lea     rbp, [rsp-1A0h]
0x18000cb23  sub     rsp, 2A0h
0x18000cb2a  mov     rax, cs:__security_cookie
0x18000cb31  xor     rax, rsp
0x18000cb34  mov     [rbp+1A0h+var_10], rax
0x18000cb3b  mov     rbx, rdx
0x18000cb3e  mov     rdi, rcx
0x18000cb41  mov     [rsp+2A0h+var_236], 0
0x18000cb46  mov     [rsp+2A0h+var_234], 208h
0x18000cb4e  lea     rax, [rbp+1A0h+var_220]
0x18000cb52  mov     [rsp+2A0h+var_230], rax
0x18000cb57  mov     [rsp+2A0h+var_228], 0
0x18000cb5f  xor     eax, eax
0x18000cb61  mov     [rbp+1A0h+var_220], ax
0x18000cb65  lea     r8, [rsp+2A0h+var_238]; struct STRU *
0x18000cb6a  call    ?GetConfigPath@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@AEAVSTRU@@@Z; ConfigPathNode::GetConfigPath(ConfigPathNavigationTree *,STRU &)
0x18000cb6f  mov     [rsp+2A0h+var_270], 0
0x18000cb76  mov     [rsp+2A0h+var_268], 0
0x18000cb7f  mov     [rsp+2A0h+var_260], 0
0x18000cb88  mov     [rsp+2A0h+var_256], 0
0x18000cb8d  mov     [rsp+2A0h+var_254], 2
0x18000cb95  lea     rax, [rsp+2A0h+var_258]
0x18000cb9a  mov     [rsp+2A0h+var_250], rax
0x18000cb9f  mov     [rsp+2A0h+var_248], 0
0x18000cba7  xor     eax, eax
0x18000cba9  mov     [rsp+2A0h+var_258], ax
0x18000cbae  mov     [rsp+2A0h+var_240], rax
0x18000cbb3  mov     r8, [rbx+0A0h]
0x18000cbba  mov     r8, [r8+10h]; struct IAppHostAdminManager *
0x18000cbbe  mov     rdx, [rsp+2A0h+var_230]; unsigned __int16 *
0x18000cbc3  lea     rcx, [rsp+2A0h+var_270]; this
0x18000cbc8  call    ?Reset@ConfigLocationsEnumerator@@QEAAXPEBGPEAUIAppHostAdminManager@@@Z; ConfigLocationsEnumerator::Reset(ushort const *,IAppHostAdminManager *)
0x18000cbcd  jmp     short loc_18000CBF8
0x18000cbcf  mov     [rsp+2A0h+var_280], 0Ah
0x18000cbd7  lea     rax, aConfigpathnode_6; "ConfigPathNodeType_Location"
0x18000cbde  mov     [rsp+2A0h+var_278], rax
0x18000cbe3  lea     r9, [rsp+2A0h+var_280]
0x18000cbe8  mov     r8, [rsp+2A0h+var_250]
0x18000cbed  mov     rdx, rbx
0x18000cbf0  mov     rcx, rdi
0x18000cbf3  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000cbf8  lea     rcx, [rsp+2A0h+var_270]; this
0x18000cbfd  call    ?MoveNext@ConfigLocationsEnumerator@@QEAA_NXZ; ConfigLocationsEnumerator::MoveNext(void)
0x18000cc02  test    al, al
0x18000cc04  jnz     short loc_18000CBCF
0x18000cc06  lea     rcx, [rsp+2A0h+var_270]; this
0x18000cc0b  call    ??1ConfigLocationsEnumerator@@QEAA@XZ; ConfigLocationsEnumerator::~ConfigLocationsEnumerator(void)
0x18000cc10  nop
0x18000cc11  lea     rcx, [rsp+2A0h+var_238]; this
0x18000cc16  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000cc1b  mov     rcx, [rbp+1A0h+var_10]
0x18000cc22  xor     rcx, rsp; StackCookie
0x18000cc25  call    __security_check_cookie
0x18000cc2a  lea     r11, [rsp+2A0h+var_s0]
0x18000cc32  mov     rbx, [r11+20h]
0x18000cc36  mov     rdi, [r11+28h]
0x18000cc3a  mov     rsp, r11
0x18000cc3d  pop     rbp
0x18000cc3e  retn
```

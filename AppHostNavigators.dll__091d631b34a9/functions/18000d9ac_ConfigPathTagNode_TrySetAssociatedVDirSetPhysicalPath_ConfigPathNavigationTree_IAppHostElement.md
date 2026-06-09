# ConfigPathTagNode::TrySetAssociatedVDirSetPhysicalPath(ConfigPathNavigationTree *,IAppHostElement *)

- ea: `0x18000d9ac`
- end: `0x18000da7b`
- name: `?TrySetAssociatedVDirSetPhysicalPath@ConfigPathTagNode@@QEAA_NPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@@Z`
- size: `207`
- prototype: `bool __fastcall(ConfigPathTagNode *__hidden this, struct ConfigPathNavigationTree *, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000d430`

## callees

- `0x1800021e0`
- `0x18000c5a4`
- `0x18000c8a8`
- `0x18000d6bc`
- `0x18000d8c4`
- `0x18000d9ac`
- `0x1800130a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConfigPathTagNode::TrySetAssociatedVDirSetPhysicalPath(
        ConfigPathTagNode *this,
        struct ConfigPathNavigationTree *a2,
        struct IAppHostElement *a3)
{
  char v6; // bl
  struct ConfigPathTagNode *v8; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v9[4]; // [rsp+28h] [rbp-D8h] BYREF
  int v10; // [rsp+2Ch] [rbp-D4h]
  unsigned __int16 *v11; // [rsp+30h] [rbp-D0h]
  int v12; // [rsp+38h] [rbp-C8h]
  __int16 v13; // [rsp+40h] [rbp-C0h] BYREF

  v9[2] = 0;
  v10 = 520;
  v11 = (unsigned __int16 *)&v13;
  v12 = 0;
  v13 = 0;
  ConfigPathNode::GetConfigPath(this, a2, (struct STRU *)v9);
  v8 = 0;
  if ( ConfigPathNavigationTree::TryGetVDirMappingOwner(a2, v11, &v8) )
  {
    v6 = 0;
  }
  else
  {
    ConfigPathNavigationTree::AddVDirMappingOwner(a2, v11, this);
    ConfigPathNode::SetAssociatedVDirPhysicalPath(this, a3);
    v6 = 1;
  }
  BUFFER::~BUFFER((BUFFER *)v9);
  return v6;
}

```

## disassembly

```asm
0x18000d9ac  mov     [rsp-8+arg_18], rbx
0x18000d9b1  push    rbp
0x18000d9b2  push    rsi
0x18000d9b3  push    rdi
0x18000d9b4  lea     rbp, [rsp-160h]
0x18000d9bc  sub     rsp, 260h
0x18000d9c3  mov     rax, cs:__security_cookie
0x18000d9ca  xor     rax, rsp
0x18000d9cd  mov     [rbp+170h+var_20], rax
0x18000d9d4  mov     rsi, r8
0x18000d9d7  mov     rdi, rdx
0x18000d9da  mov     rbx, rcx
0x18000d9dd  mov     [rsp+270h+var_246], 0
0x18000d9e2  mov     [rsp+270h+var_244], 208h
0x18000d9ea  lea     rax, [rsp+270h+var_230]
0x18000d9ef  mov     [rsp+270h+var_240], rax
0x18000d9f4  mov     [rsp+270h+var_238], 0
0x18000d9fc  xor     eax, eax
0x18000d9fe  mov     [rsp+270h+var_230], ax
0x18000da03  lea     r8, [rsp+270h+var_248]; struct STRU *
0x18000da08  call    ?GetConfigPath@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@AEAVSTRU@@@Z; ConfigPathNode::GetConfigPath(ConfigPathNavigationTree *,STRU &)
0x18000da0d  mov     [rsp+270h+var_250], 0
0x18000da16  lea     r8, [rsp+270h+var_250]; struct ConfigPathTagNode **
0x18000da1b  mov     rdx, [rsp+270h+var_240]; unsigned __int16 *
0x18000da20  mov     rcx, rdi; this
0x18000da23  call    ?TryGetVDirMappingOwner@ConfigPathNavigationTree@@QEAA_NPEBGPEAPEAVConfigPathTagNode@@@Z; ConfigPathNavigationTree::TryGetVDirMappingOwner(ushort const *,ConfigPathTagNode * *)
0x18000da28  test    al, al
0x18000da2a  jz      short loc_18000DA30
0x18000da2c  xor     ebx, ebx
0x18000da2e  jmp     short loc_18000DA4D
0x18000da30  mov     r8, rbx; struct ConfigPathTagNode *
0x18000da33  mov     rdx, [rsp+270h+var_240]; unsigned __int16 *
0x18000da38  mov     rcx, rdi; this
0x18000da3b  call    ?AddVDirMappingOwner@ConfigPathNavigationTree@@QEAAXPEBGPEAVConfigPathTagNode@@@Z; ConfigPathNavigationTree::AddVDirMappingOwner(ushort const *,ConfigPathTagNode *)
0x18000da40  mov     rdx, rsi; struct IAppHostElement *
0x18000da43  mov     rcx, rbx; this
0x18000da46  call    ?SetAssociatedVDirPhysicalPath@ConfigPathNode@@IEAAXPEAUIAppHostElement@@@Z; ConfigPathNode::SetAssociatedVDirPhysicalPath(IAppHostElement *)
0x18000da4b  mov     bl, 1
0x18000da4d  lea     rcx, [rsp+270h+var_248]; this
0x18000da52  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000da57  mov     al, bl
0x18000da59  mov     rcx, [rbp+170h+var_20]
0x18000da60  xor     rcx, rsp; StackCookie
0x18000da63  call    __security_check_cookie
0x18000da68  mov     rbx, [rsp+270h+arg_18]
0x18000da70  add     rsp, 260h
0x18000da77  pop     rdi
0x18000da78  pop     rsi
0x18000da79  pop     rbp
0x18000da7a  retn
```

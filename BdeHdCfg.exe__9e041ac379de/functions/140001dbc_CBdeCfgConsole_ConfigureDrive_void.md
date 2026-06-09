# CBdeCfgConsole::ConfigureDrive(void)

- ea: `0x140001dbc`
- end: `0x140001ec5`
- name: `?ConfigureDrive@CBdeCfgConsole@@AEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140001fac`

## callees

- `0x140001d6c`
- `0x140001dbc`
- `0x140001ecc`
- `0x140002898`
- `0x1400028d0`
- `0x1400031c4`
- `0x1400032b0`
- `0x140003554`
- `0x140003804`

## import_xrefs

- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x140001eb2`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x14000463c`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x140001eb2`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x14000463c`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001e58`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001e8d`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001e58`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001e8d`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::ConfigureDrive(CBdeCfgConsole *this)
{
  int v2; // ebx
  int v3; // eax
  CBdeCfgConsole *v4; // rcx
  int v5; // eax
  CBdeCfgConsole *v6; // rcx

  v2 = CBdeCfgConsole::Initialize(this);
  if ( v2 >= 0 )
  {
    v2 = CBdeCfgConsole::InitializeHelper(this);
    if ( v2 >= 0 )
    {
      v3 = CBdeCfgConsole::PromptForActionConfirm(this);
      v2 = v3;
      if ( v3 < 0 )
        goto LABEL_12;
      if ( v3 != 1 )
      {
        v2 = CBdeCfgConsole::ConfigureHelper(this);
        if ( v2 >= 0 )
        {
          v5 = CBdeCfgConsole::CheckAndMoveWinRE(v4);
          v2 = v5;
          if ( v5 < 0 )
          {
            CBdeCfgConsole::PrintConsoleMessage(this, v5);
            CBdeCfgConsole::PrintConsoleMessage(this, L"\r\n\r\n");
            BdeCfgLogError(0, (unsigned int)v2);
            v2 = 0;
          }
          v6 = this;
          if ( !*((_BYTE *)this + 1385) )
            goto LABEL_13;
          v3 = CBdeCfgConsole::Reboot(this);
          v2 = v3;
          if ( v3 == 1 )
          {
            v6 = this;
LABEL_13:
            CBdeCfgConsole::PrintConsoleMessage(v6, 1084227637);
            goto LABEL_14;
          }
          if ( v3 >= 0 )
            goto LABEL_14;
LABEL_12:
          BdeCfgLogError(0, (unsigned int)v3);
        }
      }
    }
  }
LABEL_14:
  if ( v2 < 0 )
    CBdeCfgConsole::PrintConsoleMessage(this, v2);
  CBdeCfgLibraryLoader::Unload((CBdeCfgConsole *)((char *)this + 8));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140001dbc  mov     [rsp+arg_8], rbx
0x140001dc1  mov     [rsp+arg_0], rcx
0x140001dc6  push    rdi
0x140001dc7  sub     rsp, 30h
0x140001dcb  mov     rdi, rcx
0x140001dce  mov     [rsp+38h+var_18], 0
0x140001dd6  call    ?Initialize@CBdeCfgConsole@@QEAAJXZ; CBdeCfgConsole::Initialize(void)
0x140001ddb  mov     ebx, eax
0x140001ddd  mov     [rsp+38h+var_18], eax
0x140001de1  test    eax, eax
0x140001de3  js      loc_140001EA0
0x140001de9  mov     rcx, rdi; this
0x140001dec  call    ?InitializeHelper@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::InitializeHelper(void)
0x140001df1  mov     ebx, eax
0x140001df3  mov     [rsp+38h+var_18], eax
0x140001df7  test    eax, eax
0x140001df9  js      loc_140001EA0
0x140001dff  mov     rcx, rdi; this
0x140001e02  call    ?PromptForActionConfirm@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::PromptForActionConfirm(void)
0x140001e07  mov     ebx, eax
0x140001e09  mov     [rsp+38h+var_18], eax
0x140001e0d  test    eax, eax
0x140001e0f  js      short loc_140001E89
0x140001e11  cmp     eax, 1
0x140001e14  jz      loc_140001EA0
0x140001e1a  mov     rcx, rdi; this
0x140001e1d  call    ?ConfigureHelper@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::ConfigureHelper(void)
0x140001e22  mov     ebx, eax
0x140001e24  mov     [rsp+38h+var_18], eax
0x140001e28  test    eax, eax
0x140001e2a  js      short loc_140001EA0
0x140001e2c  call    ?CheckAndMoveWinRE@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::CheckAndMoveWinRE(void)
0x140001e31  mov     ebx, eax
0x140001e33  mov     [rsp+38h+var_18], eax
0x140001e37  test    eax, eax
0x140001e39  jns     short loc_140001E64
0x140001e3b  mov     edx, eax; int
0x140001e3d  mov     rcx, rdi; this
0x140001e40  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140001e45  lea     rdx, asc_1400067C8; "\r\n\r\n"
0x140001e4c  mov     rcx, rdi; this
0x140001e4f  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x140001e54  mov     edx, ebx
0x140001e56  xor     ecx, ecx
0x140001e58  call    cs:__imp_BdeCfgLogError
0x140001e5e  xor     ebx, ebx
0x140001e60  mov     [rsp+38h+var_18], ebx
0x140001e64  mov     rcx, rdi; this
0x140001e67  cmp     byte ptr [rdi+569h], 0
0x140001e6e  jz      short loc_140001E95
0x140001e70  call    ?Reboot@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::Reboot(void)
0x140001e75  mov     ebx, eax
0x140001e77  mov     [rsp+38h+var_18], eax
0x140001e7b  cmp     eax, 1
0x140001e7e  jnz     short loc_140001E85
0x140001e80  mov     rcx, rdi
0x140001e83  jmp     short loc_140001E95
0x140001e85  test    eax, eax
0x140001e87  jns     short loc_140001EA0
0x140001e89  mov     edx, eax
0x140001e8b  xor     ecx, ecx
0x140001e8d  call    cs:__imp_BdeCfgLogError
0x140001e93  jmp     short loc_140001EA0
0x140001e95  mov     edx, 40A00035h; int
0x140001e9a  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140001e9f  nop
0x140001ea0  test    ebx, ebx
0x140001ea2  jns     short loc_140001EAE
0x140001ea4  mov     edx, ebx; int
0x140001ea6  mov     rcx, rdi; this
0x140001ea9  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140001eae  lea     rcx, [rdi+8]
0x140001eb2  call    cs:__imp_?Unload@CBdeCfgLibraryLoader@@QEAAXXZ; CBdeCfgLibraryLoader::Unload(void)
0x140001eb8  mov     eax, ebx
0x140001eba  mov     rbx, [rsp+38h+arg_8]
0x140001ebf  add     rsp, 30h
0x140001ec3  pop     rdi
0x140001ec4  retn
0x14000461a  push    rbp
0x14000461c  sub     rsp, 20h
0x140004620  mov     rbp, rdx
0x140004623  mov     edx, [rbp+20h]; int
0x140004626  test    edx, edx
0x140004628  jns     short loc_140004634
0x14000462a  mov     rcx, [rbp+40h]; this
0x14000462e  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x140004633  nop
0x140004634  mov     rcx, [rbp+40h]
0x140004638  add     rcx, 8
0x14000463c  call    cs:__imp_?Unload@CBdeCfgLibraryLoader@@QEAAXXZ; CBdeCfgLibraryLoader::Unload(void)
0x140004642  nop
0x140004643  add     rsp, 20h
0x140004647  pop     rbp
0x140004648  retn
```

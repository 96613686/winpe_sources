# DxDbDismHelper::Init(void)

- ea: `0x1400181fc`
- end: `0x14001826e`
- name: `?Init@DxDbDismHelper@@QEAAJXZ`
- size: `114`
- prototype: `int(DxDbDismHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140018274`

## callees

- `0x14000a4bc`
- `0x1400181fc`

## import_xrefs

- `DismApi!DismOpenSession` at `0x14001824e`
- `DismApi!DismOpenSession` at `0x14001824e`
- `DismApi!DismInitialize` at `0x140018216`
- `DismApi!DismInitialize` at `0x140018216`

## string_xrefs

- `0x14001822c`: `onecore\windows\directx\database\updater\dismhelper\dismhelper.cpp`

## pseudocode

```c
__int64 __fastcall DxDbDismHelper::Init(DxDbDismHelper *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*(_DWORD *)this )
  {
    v2 = DismInitialize(2, 0, 0);
    if ( v2 < 0 )
    {
      v3 = 19;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\dismhelper\\dismhelper.cpp",
        (const char *)(unsigned int)v2,
        v5);
      return (unsigned int)v2;
    }
    v2 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, this);
    if ( v2 < 0 )
    {
      v3 = 21;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400181fc  mov     [rsp+arg_0], rbx
0x140018201  push    rdi; int
0x140018202  sub     rsp, 20h
0x140018206  cmp     dword ptr [rcx], 0
0x140018209  mov     rdi, rcx
0x14001820c  jnz     short loc_140018261
0x14001820e  xor     edx, edx
0x140018210  xor     r8d, r8d
0x140018213  lea     ecx, [rdx+2]
0x140018216  call    cs:__imp_DismInitialize
0x14001821c  mov     ebx, eax
0x14001821e  test    eax, eax
0x140018220  jns     short loc_14001823F
0x140018222  mov     edx, 13h; void *
0x140018227  mov     rcx, [rsp+28h]; this
0x14001822c  lea     r8, aOnecoreWindows_3; "onecore\\windows\\directx\\database\\up"...
0x140018233  mov     r9d, ebx; char *
0x140018236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001823b  mov     eax, ebx
0x14001823d  jmp     short loc_140018263
0x14001823f  mov     r9, rdi
0x140018242  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x140018249  xor     r8d, r8d
0x14001824c  xor     edx, edx
0x14001824e  call    cs:__imp_DismOpenSession
0x140018254  mov     ebx, eax
0x140018256  test    eax, eax
0x140018258  jns     short loc_140018261
0x14001825a  mov     edx, 15h
0x14001825f  jmp     short loc_140018227
0x140018261  xor     eax, eax
0x140018263  mov     rbx, [rsp+28h+arg_0]
0x140018268  add     rsp, 20h
0x14001826c  pop     rdi
0x14001826d  retn
```

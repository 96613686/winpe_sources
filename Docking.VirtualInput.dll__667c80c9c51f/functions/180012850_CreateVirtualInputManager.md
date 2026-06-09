# CreateVirtualInputManager

- ea: `0x180012850`
- end: `0x18001294d`
- name: `CreateVirtualInputManager`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004ba0`
- `0x1800067a4`
- `0x18000b394`
- `0x18000b70c`
- `0x18000b97c`
- `0x18000c850`
- `0x180012850`

## pseudocode

```c
__int64 __fastcall CreateVirtualInputManager(__int64 a1)
{
  unsigned int v2; // eax
  int v3; // [rsp+20h] [rbp-28h]
  int v4; // [rsp+20h] [rbp-28h]
  unsigned int v5; // [rsp+24h] [rbp-24h]
  _QWORD v6[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Microsoft::WRL::Details::Make<Docking::VirtualInput::VirtualInputManagerServer,>(v6);
  if ( (unsigned __int8)Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(v6, 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\stubs.cpp",
      (const char *)0x8007000ELL,
      v3);
    Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(v6);
    return 2147942414LL;
  }
  else
  {
    v2 = Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::CopyTo<IInspectable>(v6, a1);
    v4 = wil::verify_BOOL<int>(v2);
    if ( v4 >= 0 )
    {
      Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(v6);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\stubs.cpp",
        (const char *)(unsigned int)v4,
        v4);
      Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(v6);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x180012850  mov     [rsp+arg_0], rcx
0x180012855  sub     rsp, 48h
0x180012859  lea     rcx, [rsp+48h+var_10]
0x18001285e  call    ??$Make@VVirtualInputManagerServer@VirtualInput@Docking@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@12@XZ; Microsoft::WRL::Details::Make<Docking::VirtualInput::VirtualInputManagerServer,>(void)
0x180012863  nop
0x180012864  xor     edx, edx
0x180012866  lea     rcx, [rsp+48h+var_10]
0x18001286b  call    ??$?8VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@YA_NAEBV?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@01@$$T@Z; Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer> const &,std::nullptr_t)
0x180012870  movzx   eax, al
0x180012873  test    eax, eax
0x180012875  jz      short loc_1800128C0
0x180012877  mov     [rsp+48h+var_14], 8007000Eh
0x18001287f  mov     rax, [rsp+48h]
0x180012884  mov     r9d, 8007000Eh; char *
0x18001288a  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180012891  mov     edx, 3Fh ; '?'; void *
0x180012896  mov     rcx, rax; this
0x180012899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001289e  nop
0x18001289f  mov     dword ptr [rsp+48h+var_24+4], 8007000Eh
0x1800128a7  lea     rcx, [rsp+48h+var_10]
0x1800128ac  call    ??1?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(void)
0x1800128b1  mov     eax, dword ptr [rsp+48h+var_24+4]
0x1800128b5  jmp     loc_180012948
0x1800128ba  xor     eax, eax
0x1800128bc  test    eax, eax
0x1800128be  jnz     short loc_180012877
0x1800128c0  xor     eax, eax
0x1800128c2  test    eax, eax
0x1800128c4  jnz     short loc_180012864
0x1800128c6  mov     rdx, [rsp+48h+arg_0]
0x1800128cb  lea     rcx, [rsp+48h+var_10]
0x1800128d0  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::CopyTo<IInspectable>(IInspectable * *)
0x1800128d5  mov     ecx, eax
0x1800128d7  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800128dc  mov     [rsp+48h+var_28], eax; int
0x1800128e0  cmp     [rsp+48h+var_28], 0
0x1800128e5  jge     short loc_18001292C
0x1800128e7  mov     eax, [rsp+48h+var_28]
0x1800128eb  mov     dword ptr [rsp+48h+var_24], eax
0x1800128ef  mov     rax, [rsp+48h]
0x1800128f4  mov     r9d, dword ptr [rsp+48h+var_24]; char *
0x1800128f9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180012900  mov     edx, 41h ; 'A'; void *
0x180012905  mov     rcx, rax; this
0x180012908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001290d  nop
0x18001290e  mov     eax, dword ptr [rsp+48h+var_24]
0x180012912  mov     [rsp+48h+var_1C], eax
0x180012916  lea     rcx, [rsp+48h+var_10]
0x18001291b  call    ??1?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(void)
0x180012920  mov     eax, [rsp+48h+var_1C]
0x180012924  jmp     short loc_180012948
0x180012926  xor     eax, eax
0x180012928  test    eax, eax
0x18001292a  jnz     short loc_1800128E7
0x18001292c  xor     eax, eax
0x18001292e  test    eax, eax
0x180012930  jnz     short loc_1800128C6
0x180012932  mov     [rsp+48h+var_18], 0
0x18001293a  lea     rcx, [rsp+48h+var_10]
0x18001293f  call    ??1?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::~ComPtr<Docking::VirtualInput::VirtualInputManagerServer>(void)
0x180012944  mov     eax, [rsp+48h+var_18]
0x180012948  add     rsp, 48h
0x18001294c  retn
```

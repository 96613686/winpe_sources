# AttemptATAppLaunchByHardwareButtons(void)

- ea: `0x1400048b8`
- end: `0x14000496c`
- name: `?AttemptATAppLaunchByHardwareButtons@@YAXXZ`
- size: `180`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b250`

## callees

- `0x1400048b8`
- `0x140005f00`
- `0x140006a78`
- `0x14000bd60`
- `0x14000bdf4`
- `0x140010244`
- `0x1400116c4`
- `0x140012640`
- `0x140015b00`

## pseudocode

```c
void AttemptATAppLaunchByHardwareButtons(void)
{
  int v0; // ebx
  struct Accommodation *v1; // rax
  void *v2; // r8
  _BYTE *v3; // [rsp+30h] [rbp-388h] BYREF
  _BYTE v4[352]; // [rsp+40h] [rbp-378h] BYREF
  unsigned __int16 v5[256]; // [rsp+1A0h] [rbp-218h] BYREF

  v5[0] = 0;
  v0 = IsInteractiveUser();
  if ( GetHardwareLaunchATApp(v0, v5) )
  {
    ATManager::ATManager((ATManager *)v4, v0);
    v1 = Accommodation::Open(v5);
    if ( v1 )
    {
      *((_BYTE *)v1 + 84) = 1;
      v3 = v4;
      StartList::Start((Start *)v4, (const wchar_t **)v1, v2, 0, 0);
      if ( v0 )
        SettingsCopier::InteractiveDesktopCopy((SettingsCopier *)&v3);
    }
    ATManager::~ATManager((ATManager *)v4);
  }
}

```

## disassembly

```asm
0x1400048b8  push    rbx
0x1400048ba  sub     rsp, 3B0h
0x1400048c1  mov     rax, cs:__security_cookie
0x1400048c8  xor     rax, rsp
0x1400048cb  mov     [rsp+3B8h+var_18], rax
0x1400048d3  xor     eax, eax
0x1400048d5  mov     [rsp+3B8h+var_218], ax
0x1400048dd  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x1400048e2  lea     rdx, [rsp+3B8h+var_218]; unsigned __int16 *
0x1400048ea  mov     ecx, eax; int
0x1400048ec  mov     ebx, eax
0x1400048ee  call    ?GetHardwareLaunchATApp@@YA_NHPEAGI@Z; GetHardwareLaunchATApp(int,ushort *,uint)
0x1400048f3  test    al, al
0x1400048f5  jz      short loc_140004953
0x1400048f7  mov     edx, ebx; int
0x1400048f9  lea     rcx, [rsp+3B8h+var_378]; this
0x1400048fe  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x140004903  lea     rcx, [rsp+3B8h+var_218]; unsigned __int16 *
0x14000490b  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x140004910  test    rax, rax
0x140004913  jz      short loc_140004949
0x140004915  lea     rcx, [rsp+3B8h+var_378]
0x14000491a  mov     byte ptr [rax+54h], 1
0x14000491e  mov     [rsp+3B8h+var_388], rcx
0x140004923  xor     r9d, r9d; int
0x140004926  lea     rcx, [rsp+3B8h+var_378]; this
0x14000492b  mov     [rsp+3B8h+var_398], 0; int
0x140004933  mov     rdx, rax; struct Accommodation *
0x140004936  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x14000493b  test    ebx, ebx
0x14000493d  jz      short loc_140004949
0x14000493f  lea     rcx, [rsp+3B8h+var_388]; this
0x140004944  call    ?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ; SettingsCopier::InteractiveDesktopCopy(void)
0x140004949  lea     rcx, [rsp+3B8h+var_378]; this
0x14000494e  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x140004953  mov     rcx, [rsp+3B8h+var_18]
0x14000495b  xor     rcx, rsp; StackCookie
0x14000495e  call    __security_check_cookie
0x140004963  add     rsp, 3B0h
0x14000496a  pop     rbx
0x14000496b  retn
```

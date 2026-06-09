# DllMain

- ea: `0x18000af3c`
- end: `0x18000b024`
- name: `DllMain`
- size: `232`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800096c4`

## callees

- `0x180007810`
- `0x18000af3c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000aff7`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000aff7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000afd1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000afd1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _QWORD *v4; // rbx
  TRACEHANDLE v5; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_18001B850 = 0;
      WPP_MAIN_CB = (__int64)&qword_18001B868;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_UtilsibGuid;
      qword_18001B898 = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      qword_18001B858 = 1;
      qword_18001B878 = 0;
      qword_18001B868 = 0;
      qword_18001B880 = 1;
      WppInitUm(hinstDLL, fdwReason, lpvReserved);
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v4 )
      {
        v5 = v4[1];
        if ( v5 )
        {
          UnregisterTraceGuids(v5);
          v4[1] = 0;
        }
        v4 = (_QWORD *)*v4;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000af3c  mov     [rsp+arg_0], rbx
0x18000af41  push    rsi
0x18000af42  sub     rsp, 20h
0x18000af46  mov     rbx, rcx
0x18000af49  test    edx, edx
0x18000af4b  jz      loc_18000AFD9
0x18000af51  cmp     edx, 1
0x18000af54  jnz     loc_18000B014
0x18000af5a  lea     rax, qword_18001B868
0x18000af61  mov     cs:qword_18001B850, 0
0x18000af6c  mov     cs:WPP_MAIN_CB, rax
0x18000af73  lea     rax, WPP_ThisDir_CTLGUID_UtilsibGuid
0x18000af7a  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000af81  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18000af88  mov     cs:qword_18001B898, rax
0x18000af8f  lea     rax, WPP_MAIN_CB
0x18000af96  mov     cs:WPP_GLOBAL_Control, rax
0x18000af9d  mov     cs:qword_18001B858, 1
0x18000afa8  mov     cs:qword_18001B878, 0
0x18000afb3  mov     cs:qword_18001B868, 0
0x18000afbe  mov     cs:qword_18001B880, 1
0x18000afc9  call    WppInitUm
0x18000afce  mov     rcx, rbx; hLibModule
0x18000afd1  call    cs:__imp_DisableThreadLibraryCalls
0x18000afd7  jmp     short loc_18000B014
0x18000afd9  mov     rbx, cs:WPP_GLOBAL_Control
0x18000afe0  lea     rsi, WPP_GLOBAL_Control
0x18000afe7  cmp     rbx, rsi
0x18000afea  jz      short loc_18000B014
0x18000afec  jmp     short loc_18000B008
0x18000afee  mov     rcx, [rbx+8]; RegistrationHandle
0x18000aff2  test    rcx, rcx
0x18000aff5  jz      short loc_18000B005
0x18000aff7  call    cs:__imp_UnregisterTraceGuids
0x18000affd  mov     qword ptr [rbx+8], 0
0x18000b005  mov     rbx, [rbx]
0x18000b008  test    rbx, rbx
0x18000b00b  jnz     short loc_18000AFEE
0x18000b00d  mov     cs:WPP_GLOBAL_Control, rsi
0x18000b014  mov     rbx, [rsp+28h+arg_0]
0x18000b019  mov     eax, 1
0x18000b01e  add     rsp, 20h
0x18000b022  pop     rsi
0x18000b023  retn
```

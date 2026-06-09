# SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::OpenECPRegKey(void)

- ea: `0x180035f60`
- end: `0x180035fd8`
- name: `?OpenECPRegKey@BrightnessDimmingControl@BatteryUsageHandlers@SystemSettings@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034b10`
- `0x180035e88`

## callees

- `0x180035f20`
- `0x180035f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f96`

## pseudocode

```c
_QWORD *__fastcall SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::OpenECPRegKey(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // r8d
  bool v5; // sf
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\whesvc", 0, 0x20119u, &v9);
  v5 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v5 = v3 < 0;
  }
  if ( v5 )
  {
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x10C, v4, (const char *)(unsigned int)v3, v7);
    *a2 = 0;
  }
  else
  {
    *a2 = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x180035f60  mov     r11, rsp
0x180035f63  mov     [r11+8], rcx
0x180035f67  push    rbx
0x180035f68  sub     rsp, 30h
0x180035f6c  mov     rbx, rdx
0x180035f6f  mov     qword ptr [r11+8], 0
0x180035f77  lea     rax, [r11+8]
0x180035f7b  mov     r9d, 20119h; samDesired
0x180035f81  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180035f88  mov     [r11-18h], rax
0x180035f8c  xor     r8d, r8d; ulOptions
0x180035f8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035f96  call    cs:__imp_RegOpenKeyExW
0x180035f9c  test    eax, eax
0x180035f9e  jle     short loc_180035FAA
0x180035fa0  movzx   eax, ax
0x180035fa3  or      eax, 80070000h
0x180035fa8  test    eax, eax
0x180035faa  jns     short loc_180035FC7
0x180035fac  mov     rcx, [rsp+38h]; this
0x180035fb1  mov     r9d, eax; char *
0x180035fb4  mov     edx, 10Ch; void *
0x180035fb9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180035fbe  mov     qword ptr [rbx], 0
0x180035fc5  jmp     short loc_180035FCF
0x180035fc7  mov     rax, [rsp+38h+arg_0]
0x180035fcc  mov     [rbx], rax
0x180035fcf  mov     rax, rbx
0x180035fd2  add     rsp, 30h
0x180035fd6  pop     rbx
0x180035fd7  retn
```

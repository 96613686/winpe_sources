# SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeSingleton::OpenECPRegKey(void)

- ea: `0x180046328`
- end: `0x1800463a0`
- name: `?OpenECPRegKey@AdaptiveModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004613c`
- `0x180046240`

## callees

- `0x1800461dc`
- `0x180046328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004635e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004635e`

## pseudocode

```c
_QWORD *__fastcall SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeSingleton::OpenECPRegKey(
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
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x58, v4, (const char *)(unsigned int)v3, v7);
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
0x180046328  mov     r11, rsp
0x18004632b  mov     [r11+8], rcx
0x18004632f  push    rbx
0x180046330  sub     rsp, 30h
0x180046334  mov     rbx, rdx
0x180046337  mov     qword ptr [r11+8], 0
0x18004633f  lea     rax, [r11+8]
0x180046343  mov     r9d, 20119h; samDesired
0x180046349  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180046350  mov     [r11-18h], rax
0x180046354  xor     r8d, r8d; ulOptions
0x180046357  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004635e  call    cs:__imp_RegOpenKeyExW
0x180046364  test    eax, eax
0x180046366  jle     short loc_180046372
0x180046368  movzx   eax, ax
0x18004636b  or      eax, 80070000h
0x180046370  test    eax, eax
0x180046372  jns     short loc_18004638F
0x180046374  mov     rcx, [rsp+38h]; this
0x180046379  mov     r9d, eax; char *
0x18004637c  mov     edx, 58h ; 'X'; void *
0x180046381  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180046386  mov     qword ptr [rbx], 0
0x18004638d  jmp     short loc_180046397
0x18004638f  mov     rax, [rsp+38h+arg_0]
0x180046394  mov     [rbx], rax
0x180046397  mov     rax, rbx
0x18004639a  add     rsp, 30h
0x18004639e  pop     rbx
0x18004639f  retn
```

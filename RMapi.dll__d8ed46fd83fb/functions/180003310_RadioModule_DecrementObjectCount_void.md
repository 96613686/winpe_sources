# RadioModule::DecrementObjectCount(void)

- ea: `0x180003310`
- end: `0x18000335a`
- name: `?DecrementObjectCount@RadioModule@@UEAAKXZ`
- size: `74`
- prototype: `unsigned int __fastcall(RadioModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fc08`

## callees

- `0x180002ec0`
- `0x180003310`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180003319`
- `combase!__imp_CoReleaseSharedService` at `0x180003319`

## pseudocode

```c
__int64 __fastcall RadioModule::DecrementObjectCount(RadioModule *this)
{
  unsigned int v1; // ebx

  v1 = CoReleaseSharedService(*((unsigned int *)this + 6));
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180003310  push    rbx
0x180003312  sub     rsp, 20h
0x180003316  mov     ecx, [rcx+18h]
0x180003319  call    cs:__imp_CoReleaseSharedService
0x18000331f  mov     ebx, eax
0x180003321  mov     rcx, cs:WPP_GLOBAL_Control
0x180003328  lea     rax, WPP_GLOBAL_Control
0x18000332f  cmp     rcx, rax
0x180003332  jz      short loc_180003352
0x180003334  test    byte ptr [rcx+1Ch], 4
0x180003338  jz      short loc_180003352
0x18000333a  mov     rcx, [rcx+10h]
0x18000333e  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003345  mov     edx, 16h
0x18000334a  mov     r9d, ebx
0x18000334d  call    WPP_SF_d
0x180003352  mov     eax, ebx
0x180003354  add     rsp, 20h
0x180003358  pop     rbx
0x180003359  retn
```

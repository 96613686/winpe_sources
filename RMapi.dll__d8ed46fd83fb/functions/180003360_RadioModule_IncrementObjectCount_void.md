# RadioModule::IncrementObjectCount(void)

- ea: `0x180003360`
- end: `0x1800033aa`
- name: `?IncrementObjectCount@RadioModule@@UEAAKXZ`
- size: `74`
- prototype: `unsigned int __fastcall(RadioModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001da90`

## callees

- `0x180002ec0`
- `0x180003360`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180003369`
- `combase!__imp_CoAddRefSharedService` at `0x180003369`

## pseudocode

```c
__int64 __fastcall RadioModule::IncrementObjectCount(RadioModule *this)
{
  unsigned int v1; // ebx

  v1 = CoAddRefSharedService(*((unsigned int *)this + 6));
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180003360  push    rbx
0x180003362  sub     rsp, 20h
0x180003366  mov     ecx, [rcx+18h]
0x180003369  call    cs:__imp_CoAddRefSharedService
0x18000336f  mov     ebx, eax
0x180003371  mov     rcx, cs:WPP_GLOBAL_Control
0x180003378  lea     rax, WPP_GLOBAL_Control
0x18000337f  cmp     rcx, rax
0x180003382  jz      short loc_1800033A2
0x180003384  test    byte ptr [rcx+1Ch], 4
0x180003388  jz      short loc_1800033A2
0x18000338a  mov     rcx, [rcx+10h]
0x18000338e  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003395  mov     edx, 15h
0x18000339a  mov     r9d, ebx
0x18000339d  call    WPP_SF_d
0x1800033a2  mov     eax, ebx
0x1800033a4  add     rsp, 20h
0x1800033a8  pop     rbx
0x1800033a9  retn
```

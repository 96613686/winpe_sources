# CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)

- ea: `0x180008e98`
- end: `0x180008ef7`
- name: `?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z`
- size: `95`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180004b7c`
- `0x180008a6c`
- `0x180008e98`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CommonUtil::OnInitializeAtStartupNoThrow(CommonUtil *this, HMODULE *a2, const unsigned __int16 *a3)
{
  int v3; // ebx

  v3 = CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback(
         a2,
         (__int64)a2,
         a3);
  if ( v3 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a47edd51fa3b305a727a406e343078e7_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008e98  mov     [rsp+arg_0], rcx
0x180008e9d  push    rbx
0x180008e9e  sub     rsp, 30h
0x180008ea2  mov     rcx, rdx
0x180008ea5  call    ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback(void *)
0x180008eaa  mov     ebx, eax
0x180008eac  jmp     short loc_180008EB2
0x180008eae  mov     ebx, dword ptr [rsp+38h+arg_0]
0x180008eb2  test    ebx, ebx
0x180008eb4  js      short loc_180008EBE
0x180008eb6  xor     eax, eax
0x180008eb8  jmp     short loc_180008EF1
0x180008eba  mov     ebx, dword ptr [rsp+38h+arg_0]
0x180008ebe  lea     rax, WPP_GLOBAL_Control
0x180008ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ecc  cmp     rcx, rax
0x180008ecf  jz      short loc_180008EEF
0x180008ed1  test    byte ptr [rcx+1Ch], 1
0x180008ed5  jz      short loc_180008EEF
0x180008ed7  mov     edx, 0Ah
0x180008edc  mov     r9d, ebx
0x180008edf  lea     r8, WPP_a47edd51fa3b305a727a406e343078e7_Traceguids
0x180008ee6  mov     rcx, [rcx+10h]
0x180008eea  call    WPP_SF_d
0x180008eef  mov     eax, ebx
0x180008ef1  add     rsp, 30h
0x180008ef5  pop     rbx
0x180008ef6  retn
```

# CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)

- ea: `0x14000f8ac`
- end: `0x14000f90b`
- name: `?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z`
- size: `95`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f850`

## callees

- `0x140003040`
- `0x14000f88c`
- `0x14000f8ac`

## pseudocode

```c
__int64 __fastcall CommonUtil::OnInitializeAtStartupNoThrow(CommonUtil *this, int (*a2)(void *), void *a3)
{
  int v3; // ebx

  v3 = CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback(a2);
  if ( v3 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_40931461d12536ea8f2e1fda7d29c7b2_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000f8ac  mov     [rsp+arg_0], rcx
0x14000f8b1  push    rbx
0x14000f8b2  sub     rsp, 30h
0x14000f8b6  mov     rcx, rdx
0x14000f8b9  call    ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback(void *)
0x14000f8be  mov     ebx, eax
0x14000f8c0  jmp     short loc_14000F8C6
0x14000f8c2  mov     ebx, dword ptr [rsp+38h+arg_0]
0x14000f8c6  test    ebx, ebx
0x14000f8c8  js      short loc_14000F8D2
0x14000f8ca  xor     eax, eax
0x14000f8cc  jmp     short loc_14000F905
0x14000f8ce  mov     ebx, dword ptr [rsp+38h+arg_0]
0x14000f8d2  lea     rax, WPP_GLOBAL_Control
0x14000f8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8e0  cmp     rcx, rax
0x14000f8e3  jz      short loc_14000F903
0x14000f8e5  test    byte ptr [rcx+1Ch], 1
0x14000f8e9  jz      short loc_14000F903
0x14000f8eb  mov     edx, 0Ah
0x14000f8f0  mov     r9d, ebx
0x14000f8f3  lea     r8, WPP_40931461d12536ea8f2e1fda7d29c7b2_Traceguids
0x14000f8fa  mov     rcx, [rcx+10h]
0x14000f8fe  call    WPP_SF_d
0x14000f903  mov     eax, ebx
0x14000f905  add     rsp, 30h
0x14000f909  pop     rbx
0x14000f90a  retn
```

# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x140011c80`
- end: `0x140011cbc`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140010f04`
- `0x140011c80`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize(
        __int64 a1,
        __int64 a2,
        void *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax

  v3 = a1 - 40;
  if ( *(_BYTE *)(a1 - 40 + 72) )
    return 2147942487LL;
  *(_BYTE *)(v3 + 72) = 1;
  result = CommonUtil::OnInitializeAtStartupNoThrow(
             (CommonUtil *)CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback,
             (int (*)(void *))(a1 - 40),
             a3);
  if ( (int)result >= 0 )
    return 0;
  *(_BYTE *)(v3 + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x140011c80  push    rbx
0x140011c82  sub     rsp, 20h
0x140011c86  lea     rbx, [rcx-28h]
0x140011c8a  cmp     byte ptr [rbx+48h], 0
0x140011c8e  jz      short loc_140011C97
0x140011c90  mov     eax, 80070057h
0x140011c95  jmp     short loc_140011CB6
0x140011c97  mov     rdx, rbx; int (*)(void *)
0x140011c9a  mov     byte ptr [rbx+48h], 1
0x140011c9e  lea     rcx, ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; this
0x140011ca5  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x140011caa  test    eax, eax
0x140011cac  jns     short loc_140011CB4
0x140011cae  mov     byte ptr [rbx+48h], 0
0x140011cb2  jmp     short loc_140011CB6
0x140011cb4  xor     eax, eax
0x140011cb6  add     rsp, 20h
0x140011cba  pop     rbx
0x140011cbb  retn
```

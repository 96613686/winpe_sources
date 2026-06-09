# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpCriticalSection>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x14001cd60`
- end: `0x14001cda1`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004b3c`
- `0x14001cd60`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpCriticalSection>>::OnInitialize(
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
             (CommonUtil *)CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpCriticalSection>>::OnInitializeCallback,
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
0x14001cd60  push    rbx
0x14001cd62  sub     rsp, 20h
0x14001cd66  lea     rbx, [rcx-28h]
0x14001cd6a  cmp     byte ptr [rbx+48h], 0
0x14001cd6e  jz      short loc_14001CD77
0x14001cd70  mov     eax, 80070057h
0x14001cd75  jmp     short loc_14001CD9B
0x14001cd77  mov     rdx, rbx; int (*)(void *)
0x14001cd7a  mov     byte ptr [rbx+48h], 1
0x14001cd7e  lea     rcx, ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; this
0x14001cd85  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x14001cd8a  mov     ecx, eax
0x14001cd8c  shr     ecx, 1Fh
0x14001cd8f  test    cl, cl
0x14001cd91  jz      short loc_14001CD99
0x14001cd93  mov     byte ptr [rbx+48h], 0
0x14001cd97  jmp     short loc_14001CD9B
0x14001cd99  xor     eax, eax
0x14001cd9b  add     rsp, 20h
0x14001cd9f  pop     rbx
0x14001cda0  retn
```

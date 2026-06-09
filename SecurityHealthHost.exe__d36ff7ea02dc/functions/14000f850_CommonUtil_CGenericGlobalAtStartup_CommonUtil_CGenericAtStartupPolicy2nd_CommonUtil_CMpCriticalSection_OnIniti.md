# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x14000f850`
- end: `0x14000f885`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(CommonUtil *, __int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000f850`
- `0x14000f8ac`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize(
        CommonUtil *a1,
        __int64 a2,
        void *a3)
{
  char *v3; // rbx
  __int64 result; // rax

  v3 = (char *)a1 - 40;
  if ( *((_BYTE *)a1 + 32) )
    return 2147942487LL;
  v3[72] = 1;
  result = CommonUtil::OnInitializeAtStartupNoThrow(a1, (int (*)(void *))((char *)a1 - 40), a3);
  if ( (int)result >= 0 )
    return 0;
  v3[72] = 0;
  return result;
}

```

## disassembly

```asm
0x14000f850  push    rbx
0x14000f852  sub     rsp, 20h
0x14000f856  lea     rbx, [rcx-28h]
0x14000f85a  cmp     byte ptr [rbx+48h], 0
0x14000f85e  jz      short loc_14000F867
0x14000f860  mov     eax, 80070057h
0x14000f865  jmp     short loc_14000F87F
0x14000f867  mov     rdx, rbx; int (*)(void *)
0x14000f86a  mov     byte ptr [rbx+48h], 1
0x14000f86e  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x14000f873  test    eax, eax
0x14000f875  jns     short loc_14000F87D
0x14000f877  mov     byte ptr [rbx+48h], 0
0x14000f87b  jmp     short loc_14000F87F
0x14000f87d  xor     eax, eax
0x14000f87f  add     rsp, 20h
0x14000f883  pop     rbx
0x14000f884  retn
```

# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpCriticalSection>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x14001cd20`
- end: `0x14001cd52`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000404c`
- `0x14001cd20`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpCriticalSection>>::OnDestroy(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = a1 - 40;
  if ( *(_BYTE *)(a1 - 40 + 72) )
  {
    *(_BYTE *)(v1 + 72) = 0;
    CommonUtil::CMpCriticalSection::~CMpCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
    result = 0;
    *(_OWORD *)v1 = 0;
    *(_OWORD *)(v1 + 16) = 0;
    *(_QWORD *)(v1 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001cd20  push    rbx
0x14001cd22  sub     rsp, 20h
0x14001cd26  lea     rbx, [rcx-28h]
0x14001cd2a  cmp     byte ptr [rbx+48h], 0
0x14001cd2e  jz      short loc_14001CD4C
0x14001cd30  mov     rcx, rbx; lpCriticalSection
0x14001cd33  mov     byte ptr [rbx+48h], 0
0x14001cd37  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x14001cd3c  xorps   xmm0, xmm0
0x14001cd3f  xor     eax, eax
0x14001cd41  movups  xmmword ptr [rbx], xmm0
0x14001cd44  movups  xmmword ptr [rbx+10h], xmm0
0x14001cd48  mov     [rbx+20h], rax
0x14001cd4c  add     rsp, 20h
0x14001cd50  pop     rbx
0x14001cd51  retn
```

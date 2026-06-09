# CMsMpSimpleConfig::Initialize(void)

- ea: `0x180004ccc`
- end: `0x180004dcc`
- name: `?Initialize@CMsMpSimpleConfig@@QEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(CMsMpSimpleConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002a60`

## callees

- `0x180004ccc`
- `0x180005f88`
- `0x18000a010`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180004db5`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180004db5`
- `mpclient!MpConfigUninitialize` at `0x180004ce0`
- `mpclient!MpConfigUninitialize` at `0x180004ce0`
- `mpclient!MpConfigInitialize` at `0x180004cee`
- `mpclient!MpConfigInitialize` at `0x180004cee`

## pseudocode

```c
__int64 __fastcall CMsMpSimpleConfig::Initialize(CMsMpSimpleConfig *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  int v4; // ebx
  void (__fastcall ***v5)(_QWORD, __int64); // r8
  __int64 v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 9) )
  {
    MpConfigUninitialize();
    *((_QWORD *)this + 9) = 0;
  }
  result = MpConfigInitialize();
  if ( (int)result < 0 )
    return result;
  *((_QWORD *)this + 9) = 305419896;
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 8) == 1 )
    {
      *(_DWORD *)(v3 + 8) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) > 1 )
    {
LABEL_9:
      *((_QWORD *)this + 10) = 0;
      goto LABEL_10;
    }
    (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    goto LABEL_9;
  }
LABEL_10:
  v8 = 0;
  v4 = CommonUtil::CreateNewRefObject<MpConfigUtils::CSimpleMpConfig>(&v8);
  if ( v4 < 0 )
  {
    v5 = (void (__fastcall ***)(_QWORD, __int64))v8;
    if ( v8 )
    {
      if ( *(_DWORD *)(v8 + 8) == 1 )
      {
        *(_DWORD *)(v8 + 8) = 0;
        goto LABEL_15;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) <= 1 )
      {
LABEL_15:
        if ( v5 )
          (**v5)(v5, 1);
      }
    }
    return (unsigned int)v4;
  }
  v6 = v8;
  v7 = (struct _RTL_CRITICAL_SECTION *)(v8 + 16);
  *(_DWORD *)(v8 + 28) = 0;
  InitializeCriticalSectionAndSpinCount(v7, 0);
  result = 0;
  *((_QWORD *)this + 10) = v6;
  return result;
}

```

## disassembly

```asm
0x180004ccc  mov     [rsp+arg_8], rbx
0x180004cd1  push    rdi
0x180004cd2  sub     rsp, 20h
0x180004cd6  cmp     qword ptr [rcx+48h], 0
0x180004cdb  mov     rdi, rcx
0x180004cde  jz      short loc_180004CEE
0x180004ce0  call    cs:__imp_MpConfigUninitialize
0x180004ce6  mov     qword ptr [rdi+48h], 0
0x180004cee  call    cs:__imp_MpConfigInitialize
0x180004cf4  test    eax, eax
0x180004cf6  js      loc_180004DC1
0x180004cfc  mov     qword ptr [rdi+48h], 12345678h
0x180004d04  mov     rcx, [rdi+50h]
0x180004d08  test    rcx, rcx
0x180004d0b  jz      short loc_180004D43
0x180004d0d  mov     eax, [rcx+8]
0x180004d10  cmp     eax, 1
0x180004d13  jnz     short loc_180004D1E
0x180004d15  mov     dword ptr [rcx+8], 0
0x180004d1c  jmp     short loc_180004D2B
0x180004d1e  or      eax, 0FFFFFFFFh
0x180004d21  lock xadd [rcx+8], eax
0x180004d26  sub     eax, 1
0x180004d29  jg      short loc_180004D3B
0x180004d2b  mov     rax, [rcx]
0x180004d2e  mov     edx, 1
0x180004d33  mov     rax, [rax]
0x180004d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3b  mov     qword ptr [rdi+50h], 0
0x180004d43  lea     rcx, [rsp+28h+arg_0]
0x180004d48  mov     [rsp+28h+arg_0], 0
0x180004d51  call    ??$CreateNewRefObject@VCSimpleMpConfig@MpConfigUtils@@@CommonUtil@@YAJPEAPEAVCSimpleMpConfig@MpConfigUtils@@@Z; CommonUtil::CreateNewRefObject<MpConfigUtils::CSimpleMpConfig>(MpConfigUtils::CSimpleMpConfig * *)
0x180004d56  mov     ebx, eax
0x180004d58  test    eax, eax
0x180004d5a  jns     short loc_180004DA3
0x180004d5c  mov     r8, [rsp+28h+arg_0]
0x180004d61  test    r8, r8
0x180004d64  jz      short loc_180004D9F
0x180004d66  mov     ecx, [r8+8]
0x180004d6a  cmp     ecx, 1
0x180004d6d  jnz     short loc_180004D79
0x180004d6f  mov     dword ptr [r8+8], 0
0x180004d77  jmp     short loc_180004D87
0x180004d79  or      eax, 0FFFFFFFFh
0x180004d7c  lock xadd [r8+8], eax
0x180004d82  sub     eax, 1
0x180004d85  jg      short loc_180004D9F
0x180004d87  test    r8, r8
0x180004d8a  jz      short loc_180004D9F
0x180004d8c  mov     rax, [r8]
0x180004d8f  mov     edx, 1
0x180004d94  mov     rcx, r8
0x180004d97  mov     rax, [rax]
0x180004d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9f  mov     eax, ebx
0x180004da1  jmp     short loc_180004DC1
0x180004da3  mov     rbx, [rsp+28h+arg_0]
0x180004da8  xor     edx, edx; dwSpinCount
0x180004daa  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004dae  mov     dword ptr [rcx+0Ch], 0
0x180004db5  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004dbb  xor     eax, eax
0x180004dbd  mov     [rdi+50h], rbx
0x180004dc1  mov     rbx, [rsp+28h+arg_8]
0x180004dc6  add     rsp, 20h
0x180004dca  pop     rdi
0x180004dcb  retn
```

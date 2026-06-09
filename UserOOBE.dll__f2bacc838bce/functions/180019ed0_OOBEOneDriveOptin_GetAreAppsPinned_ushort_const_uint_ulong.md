# OOBEOneDriveOptin::GetAreAppsPinned(ushort const *,uint *,ulong *)

- ea: `0x180019ed0`
- end: `0x180019f50`
- name: `?GetAreAppsPinned@OOBEOneDriveOptin@@UEAAJPEBGPEAIPEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007134`
- `0x180017bbc`
- `0x1800183b4`
- `0x180019ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f14`

## string_xrefs

- `0x180019f30`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall OOBEOneDriveOptin::GetAreAppsPinned(
        OOBEOneDriveOptin *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const unsigned __int16 *v14; // [rsp+68h] [rbp+10h] BYREF
  unsigned int *v15; // [rsp+70h] [rbp+18h] BYREF
  unsigned int *v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = a4;
  v15 = a3;
  v14 = a2;
  *a3 = 0;
  *v16 = 0;
  v4 = lambda_cf59f7f2adf01739b63675bbfd49b35b_::_lambda_cf59f7f2adf01739b63675bbfd49b35b_(
         (unsigned int)&v12,
         (_DWORD)this,
         (unsigned int)&v14,
         (unsigned int)&v15,
         (__int64)&v16);
  CurrentThreadId = GetCurrentThreadId();
  v8 = Windows::Internal::ComTaskPool::QueueTask__lambda_cf59f7f2adf01739b63675bbfd49b35b___(
         v7,
         v6,
         CurrentThreadId,
         v4);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x154,
    (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v8,
    v11);
  return v9;
}

```

## disassembly

```asm
0x180019ed0  mov     r11, rsp
0x180019ed3  mov     [r11+20h], r9
0x180019ed7  mov     [r11+18h], r8
0x180019edb  mov     [r11+10h], rdx
0x180019edf  push    rbx
0x180019ee0  sub     rsp, 50h
0x180019ee4  mov     dword ptr [r8], 0
0x180019eeb  lea     r9, [r11+18h]
0x180019eef  mov     rax, [r11+20h]
0x180019ef3  lea     r8, [r11+10h]
0x180019ef7  mov     rdx, rcx
0x180019efa  lea     rcx, [r11-28h]
0x180019efe  mov     dword ptr [rax], 0
0x180019f04  lea     rax, [r11+20h]
0x180019f08  mov     [r11-38h], rax
0x180019f0c  call    _lambda_cf59f7f2adf01739b63675bbfd49b35b____lambda_cf59f7f2adf01739b63675bbfd49b35b_
0x180019f11  mov     rbx, rax
0x180019f14  call    cs:__imp_GetCurrentThreadId
0x180019f1a  mov     r8d, eax
0x180019f1d  mov     r9, rbx
0x180019f20  call    Windows__Internal__ComTaskPool__QueueTask__lambda_cf59f7f2adf01739b63675bbfd49b35b___
0x180019f25  mov     ebx, eax
0x180019f27  test    eax, eax
0x180019f29  jns     short loc_180019F48
0x180019f2b  mov     rcx, [rsp+58h]; this
0x180019f30  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019f37  mov     r9d, eax; char *
0x180019f3a  mov     edx, 154h; void *
0x180019f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f44  mov     eax, ebx
0x180019f46  jmp     short loc_180019F4A
0x180019f48  xor     eax, eax
0x180019f4a  add     rsp, 50h
0x180019f4e  pop     rbx
0x180019f4f  retn
```

# BCryptIumRpcHandleCleanup(BCRYPTIUM_CONTEXT *)

- ea: `0x140008ef4`
- end: `0x140008f85`
- name: `?BCryptIumRpcHandleCleanup@@YAXPEAUBCRYPTIUM_CONTEXT@@@Z`
- size: `145`
- prototype: `void __fastcall(struct BCRYPTIUM_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000825c`

## callees

- `0x140008ef4`
- `0x14000bf80`
- `0x14001193c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140008f3b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140008f3b`
- `ntdll!RtlDeleteCriticalSection` at `0x140008f4d`
- `ntdll!RtlDeleteCriticalSection` at `0x140008f4d`

## pseudocode

```c
void __fastcall BCryptIumRpcHandleCleanup(struct BCRYPTIUM_CONTEXT *a1)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  RundownBCryptIsoObj(a1);
  LocalFree(*((HLOCAL *)a1 + 9));
  *((_QWORD *)a1 + 9) = 0;
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
}

```

## disassembly

```asm
0x140008ef4  mov     [rsp+arg_0], rbx
0x140008ef9  push    rdi
0x140008efa  sub     rsp, 20h
0x140008efe  mov     rbx, rcx
0x140008f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f08  lea     rdi, WPP_GLOBAL_Control
0x140008f0f  cmp     rcx, rdi
0x140008f12  jz      short loc_140008F2F
0x140008f14  test    byte ptr [rcx+1Ch], 4
0x140008f18  jz      short loc_140008F2F
0x140008f1a  mov     rcx, [rcx+10h]
0x140008f1e  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140008f25  mov     edx, 37h ; '7'
0x140008f2a  call    WPP_SF_
0x140008f2f  mov     rcx, rbx; struct BCRYPTIUM_CONTEXT *
0x140008f32  call    ?RundownBCryptIsoObj@@YAXPEAUBCRYPTIUM_CONTEXT@@@Z; RundownBCryptIsoObj(BCRYPTIUM_CONTEXT *)
0x140008f37  mov     rcx, [rbx+48h]; hMem
0x140008f3b  call    cs:__imp_LocalFree
0x140008f41  lea     rcx, [rbx+18h]; CriticalSection
0x140008f45  mov     qword ptr [rbx+48h], 0
0x140008f4d  call    cs:__imp_RtlDeleteCriticalSection
0x140008f53  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f5a  cmp     rcx, rdi
0x140008f5d  jz      short loc_140008F7A
0x140008f5f  test    byte ptr [rcx+1Ch], 4
0x140008f63  jz      short loc_140008F7A
0x140008f65  mov     rcx, [rcx+10h]
0x140008f69  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140008f70  mov     edx, 39h ; '9'
0x140008f75  call    WPP_SF_
0x140008f7a  mov     rbx, [rsp+28h+arg_0]
0x140008f7f  add     rsp, 20h
0x140008f83  pop     rdi
0x140008f84  retn
```

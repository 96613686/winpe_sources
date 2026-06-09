# PnpUtilsSelectionInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)

- ea: `0x14002a8e0`
- end: `0x14002aa21`
- name: `?PnpUtilsSelectionInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z`
- size: `321`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1400070bc`
- `0x140023f6c`
- `0x14002a8e0`
- `0x14002b7ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002a99d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002a99d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a9ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002a9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a941`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a923`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a963`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002aa0b`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a923`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a963`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002aa0b`

## string_xrefs

- `0x14002a9f0`: `Unable to add '%ws' to selected extension list. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall PnpUtilsSelectionInfCallback(__int64 a1, const unsigned __int16 *a2, __int64 a3, int a4, __int64 a5)
{
  _QWORD *v7; // rsi
  DWORD LastError; // eax
  __int64 v9; // rcx
  const char *v10; // r9
  __int64 v11; // rax
  unsigned int v12; // esi
  unsigned __int16 *v13; // rax
  __int64 v15; // [rsp+28h] [rbp-30h]

  v7 = (_QWORD *)(a5 + 40);
  if ( *(_DWORD *)(a1 + 68) != 2 )
    DevRtlWriteTextLog(*v7, 512, 2, "Driver package '%ws' is unexpected type (%d)", a2, *(_DWORD *)(a1 + 68));
  if ( !(unsigned int)PnpUtilsDriverPackageAppliesToDevNode(*(_QWORD *)a5, *(unsigned int *)(a5 + 8), 0, a2) )
  {
    LastError = GetLastError();
    v9 = *v7;
    if ( !LastError )
    {
      DevRtlWriteTextLog(v9, 512, 6, "Driver package '%ws' does not apply to this device.", a2);
      return 1;
    }
    v10 = "Unable to determine whether driver package '%ws' applies to this device. Error = 0x%08X";
LABEL_15:
    LODWORD(v15) = LastError;
    DevRtlWriteTextLog(v9, 512, 2, v10, a2, v15);
    return 1;
  }
  if ( a4 != 1 )
  {
    LastError = pSetupAppendToStringArray(a5 + 24, a5 + 32, a2, 0);
    if ( !LastError )
      return 1;
    v9 = *v7;
    v10 = "Unable to add '%ws' to selected extension list. Error = 0x%08X";
    goto LABEL_15;
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = v11 + 1;
  v13 = (unsigned __int16 *)HeapAlloc(hHeap, 0, (unsigned int)(2 * (v11 + 1)));
  *(_QWORD *)(a5 + 16) = v13;
  if ( v13 && StringCchCopyW(v13, v12, a2) < 0 )
  {
    HeapFree(hHeap, 0, *(LPVOID *)(a5 + 16));
    *(_QWORD *)(a5 + 16) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14002a8e0  push    rbx
0x14002a8e2  push    rbp
0x14002a8e3  push    rsi
0x14002a8e4  push    rdi
0x14002a8e5  push    r14
0x14002a8e7  sub     rsp, 30h
0x14002a8eb  mov     rdi, [rsp+58h+arg_20]
0x14002a8f3  mov     ebp, r9d
0x14002a8f6  mov     eax, [rcx+44h]
0x14002a8f9  mov     rbx, rdx
0x14002a8fc  lea     rsi, [rdi+28h]
0x14002a900  cmp     eax, 2
0x14002a903  jz      short loc_14002A929
0x14002a905  mov     rcx, [rsi]
0x14002a908  lea     r9, aDriverPackageW_0; "Driver package '%ws' is unexpected type"...
0x14002a90f  mov     dword ptr [rsp+58h+var_30], eax
0x14002a913  mov     r8d, 2
0x14002a919  mov     [rsp+58h+var_38], rdx
0x14002a91e  mov     edx, 200h
0x14002a923  call    cs:__imp_DevRtlWriteTextLog
0x14002a929  mov     edx, [rdi+8]
0x14002a92c  mov     r9, rbx
0x14002a92f  mov     rcx, [rdi]
0x14002a932  xor     r8d, r8d
0x14002a935  call    PnpUtilsDriverPackageAppliesToDevNode
0x14002a93a  xor     r14d, r14d
0x14002a93d  test    eax, eax
0x14002a93f  jnz     short loc_14002A97A
0x14002a941  call    cs:__imp_GetLastError
0x14002a947  mov     rcx, [rsi]
0x14002a94a  mov     edx, 200h
0x14002a94f  test    eax, eax
0x14002a951  jnz     short loc_14002A96E
0x14002a953  lea     r9, aDriverPackageW_1; "Driver package '%ws' does not apply to "...
0x14002a95a  mov     [rsp+58h+var_38], rbx
0x14002a95f  lea     r8d, [r14+6]
0x14002a963  call    cs:__imp_DevRtlWriteTextLog
0x14002a969  jmp     loc_14002AA11
0x14002a96e  lea     r9, aUnableToDeterm_0; "Unable to determine whether driver pack"...
0x14002a975  jmp     loc_14002A9FC
0x14002a97a  cmp     ebp, 1
0x14002a97d  jnz     short loc_14002A9D6
0x14002a97f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002a983  inc     rax
0x14002a986  cmp     [rbx+rax*2], r14w
0x14002a98b  jnz     short loc_14002A983
0x14002a98d  mov     rcx, cs:hHeap; hHeap
0x14002a994  lea     esi, [rax+1]
0x14002a997  lea     r8d, [rsi+rsi]; dwBytes
0x14002a99b  xor     edx, edx; dwFlags
0x14002a99d  call    cs:__imp_HeapAlloc
0x14002a9a3  mov     [rdi+10h], rax
0x14002a9a7  test    rax, rax
0x14002a9aa  jz      short loc_14002AA11
0x14002a9ac  mov     edx, esi; unsigned __int64
0x14002a9ae  mov     r8, rbx; unsigned __int16 *
0x14002a9b1  mov     rcx, rax; unsigned __int16 *
0x14002a9b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002a9b9  test    eax, eax
0x14002a9bb  jns     short loc_14002AA11
0x14002a9bd  mov     r8, [rdi+10h]; lpMem
0x14002a9c1  xor     edx, edx; dwFlags
0x14002a9c3  mov     rcx, cs:hHeap; hHeap
0x14002a9ca  call    cs:__imp_HeapFree
0x14002a9d0  mov     [rdi+10h], r14
0x14002a9d4  jmp     short loc_14002AA11
0x14002a9d6  lea     rdx, [rdi+20h]
0x14002a9da  xor     r9d, r9d
0x14002a9dd  lea     rcx, [rdi+18h]
0x14002a9e1  mov     r8, rbx
0x14002a9e4  call    pSetupAppendToStringArray
0x14002a9e9  test    eax, eax
0x14002a9eb  jz      short loc_14002AA11
0x14002a9ed  mov     rcx, [rsi]
0x14002a9f0  lea     r9, aUnableToAddWsT_0; "Unable to add '%ws' to selected extensi"...
0x14002a9f7  mov     edx, 200h
0x14002a9fc  mov     dword ptr [rsp+58h+var_30], eax
0x14002aa00  mov     r8d, 2
0x14002aa06  mov     [rsp+58h+var_38], rbx
0x14002aa0b  call    cs:__imp_DevRtlWriteTextLog
0x14002aa11  mov     eax, 1
0x14002aa16  add     rsp, 30h
0x14002aa1a  pop     r14
0x14002aa1c  pop     rdi
0x14002aa1d  pop     rsi
0x14002aa1e  pop     rbp
0x14002aa1f  pop     rbx
0x14002aa20  retn
```

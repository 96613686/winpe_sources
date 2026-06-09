# WctWaitUntilThreadIsBlocked

- ea: `0x18005f0b4`
- end: `0x18005f207`
- name: `WctWaitUntilThreadIsBlocked`
- size: `339`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002e908`
- `0x18005c8fc`

## callees

- `0x180004bb4`
- `0x18001c650`
- `0x18001fe24`
- `0x180027748`
- `0x1800517cc`
- `0x18005f0b4`
- `0x18005f4a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f17f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f140`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f11c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f1b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f11c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f1b1`

## pseudocode

```c
__int64 __fastcall WctWaitUntilThreadIsBlocked(unsigned int a1, int a2)
{
  int v4; // edi
  unsigned int v5; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int ThreadWaitStatus; // eax
  void *v8; // r11
  unsigned int v9; // esi
  _BYTE v11[68]; // [rsp+20h] [rbp-C8h] BYREF
  int v12; // [rsp+64h] [rbp-84h]
  int v13; // [rsp+68h] [rbp-80h]
  struct _SYSTEM_PROCESS_INFORMATION *v14; // [rsp+100h] [rbp+18h] BYREF

  memset_0(v11, 0, 0x88u);
  v4 = 10;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  Sleep(0x64u);
  v5 = 1;
  while ( v4 && !(unsigned int)WctCreateSystemSnapshot(&v14) )
  {
    CurrentProcessId = GetCurrentProcessId();
    ThreadWaitStatus = WctGetThreadWaitStatus(
                         CurrentProcessId,
                         a1,
                         v14,
                         (struct _SYSTEM_EXTENDED_THREAD_INFORMATION *)v11);
    v14 = 0;
    v9 = ThreadWaitStatus;
    if ( v8 )
      HeapFree(g_hWerheap, 0, v8);
    if ( v9 )
      break;
    if ( v12 == 5 && a2 == v13 )
      goto LABEL_17;
    if ( (unsigned int)(v12 - 1) > 1 && (v12 != 5 || v13) )
      break;
    --v4;
    Sleep(0x1F4u);
  }
  v5 = 0;
LABEL_17:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v14);
  return v5;
}

```

## disassembly

```asm
0x18005f0b4  push    rbx
0x18005f0b6  push    rbp
0x18005f0b7  push    rsi
0x18005f0b8  push    rdi
0x18005f0b9  push    r14
0x18005f0bb  push    r15
0x18005f0bd  sub     rsp, 0B8h
0x18005f0c4  mov     ebp, edx
0x18005f0c6  mov     r14d, ecx
0x18005f0c9  xor     edx, edx; Val
0x18005f0cb  lea     rcx, [rsp+0E8h+var_C8]; void *
0x18005f0d0  mov     r8d, 88h; Size
0x18005f0d6  call    memset_0
0x18005f0db  mov     edi, 0Ah
0x18005f0e0  mov     [rsp+0E8h+arg_10], 0
0x18005f0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f0f3  lea     r15, WPP_GLOBAL_Control
0x18005f0fa  cmp     rcx, r15
0x18005f0fd  jz      short loc_18005F117
0x18005f0ff  test    byte ptr [rcx+1Ch], 4
0x18005f103  jz      short loc_18005F117
0x18005f105  mov     rcx, [rcx+10h]
0x18005f109  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f110  mov     edx, edi
0x18005f112  call    WPP_SF_
0x18005f117  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18005f11c  call    cs:__imp_Sleep
0x18005f122  mov     ebx, 1
0x18005f127  test    edi, edi
0x18005f129  jz      loc_18005F1BC
0x18005f12f  lea     rcx, [rsp+0E8h+arg_10]
0x18005f137  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18005f13c  test    eax, eax
0x18005f13e  jnz     short loc_18005F1BC
0x18005f140  call    cs:__imp_GetCurrentProcessId
0x18005f146  mov     r11, [rsp+0E8h+arg_10]
0x18005f14e  lea     r9, [rsp+0E8h+var_C8]; struct _SYSTEM_EXTENDED_THREAD_INFORMATION *
0x18005f153  mov     r8, r11; struct _SYSTEM_PROCESS_INFORMATION *
0x18005f156  mov     edx, r14d; unsigned int
0x18005f159  mov     ecx, eax; unsigned int
0x18005f15b  call    ?WctGetThreadWaitStatus@@YAKKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_SYSTEM_EXTENDED_THREAD_INFORMATION@@@Z; WctGetThreadWaitStatus(ulong,ulong,_SYSTEM_PROCESS_INFORMATION *,_SYSTEM_EXTENDED_THREAD_INFORMATION *)
0x18005f160  mov     [rsp+0E8h+arg_10], 0
0x18005f16c  mov     esi, eax
0x18005f16e  test    r11, r11
0x18005f171  jz      short loc_18005F185
0x18005f173  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005f17a  mov     r8, r11; lpMem
0x18005f17d  xor     edx, edx; dwFlags
0x18005f17f  call    cs:__imp_HeapFree
0x18005f185  test    esi, esi
0x18005f187  jnz     short loc_18005F1BC
0x18005f189  mov     ecx, [rsp+0E8h+var_84]
0x18005f18d  mov     edx, [rsp+0E8h+var_80]
0x18005f191  cmp     ecx, 5
0x18005f194  jnz     short loc_18005F19A
0x18005f196  cmp     ebp, edx
0x18005f198  jz      short loc_18005F1BE
0x18005f19a  lea     eax, [rcx-1]
0x18005f19d  cmp     eax, ebx
0x18005f19f  jbe     short loc_18005F1AA
0x18005f1a1  cmp     ecx, 5
0x18005f1a4  jnz     short loc_18005F1BC
0x18005f1a6  test    edx, edx
0x18005f1a8  jnz     short loc_18005F1BC
0x18005f1aa  dec     edi
0x18005f1ac  mov     ecx, 1F4h; dwMilliseconds
0x18005f1b1  call    cs:__imp_Sleep
0x18005f1b7  jmp     loc_18005F127
0x18005f1bc  xor     ebx, ebx
0x18005f1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f1c5  cmp     rcx, r15
0x18005f1c8  jz      short loc_18005F1E8
0x18005f1ca  test    byte ptr [rcx+1Ch], 4
0x18005f1ce  jz      short loc_18005F1E8
0x18005f1d0  mov     rcx, [rcx+10h]
0x18005f1d4  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f1db  mov     edx, 0Bh
0x18005f1e0  mov     r9d, ebx
0x18005f1e3  call    WPP_SF_d
0x18005f1e8  lea     rcx, [rsp+0E8h+arg_10]; void *
0x18005f1f0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005f1f5  mov     eax, ebx
0x18005f1f7  add     rsp, 0B8h
0x18005f1fe  pop     r15
0x18005f200  pop     r14
0x18005f202  pop     rdi
0x18005f203  pop     rsi
0x18005f204  pop     rbp
0x18005f205  pop     rbx
0x18005f206  retn
```

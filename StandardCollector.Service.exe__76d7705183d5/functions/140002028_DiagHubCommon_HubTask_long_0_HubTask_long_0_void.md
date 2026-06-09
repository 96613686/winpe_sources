# DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)

- ea: `0x140002028`
- end: `0x1400020ef`
- name: `??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001e6c`
- `0x1400021a0`

## callees

- `0x140002028`
- `0x140014c70`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140002069`
- `KERNEL32!SetEvent` at `0x140002069`
- `KERNEL32!WaitForSingleObject` at `0x14000204a`
- `KERNEL32!WaitForSingleObject` at `0x14000207d`
- `KERNEL32!WaitForSingleObject` at `0x14000204a`
- `KERNEL32!WaitForSingleObject` at `0x14000207d`
- `KERNEL32!GetLastError` at `0x140002087`
- `KERNEL32!GetLastError` at `0x140002087`
- `KERNEL32!CloseHandle` at `0x14000209f`
- `KERNEL32!CloseHandle` at `0x1400020d6`
- `KERNEL32!CloseHandle` at `0x14000209f`
- `KERNEL32!CloseHandle` at `0x1400020d6`

## pseudocode

```c
int __fastcall DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(__int64 a1, __int64 a2)
{
  void **v2; // rax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx

  v2 = &DiagHubCommon::HubTask<long,0>::`vftable';
  *(_QWORD *)a1 = &DiagHubCommon::HubTask<long,0>::`vftable';
  v4 = *(void **)(a1 + 8);
  if ( v4 )
  {
    LODWORD(v2) = WaitForSingleObject(v4, 0);
    if ( (_DWORD)v2 )
    {
      if ( *(_QWORD *)(a1 + 8) )
      {
        LODWORD(v2) = *(_DWORD *)(a1 + 96) >> 31;
        if ( *(int *)(a1 + 96) >= 0 )
          LODWORD(v2) = SetEvent(*(HANDLE *)(a1 + 88));
      }
      v5 = *(void **)(a1 + 8);
      if ( v5 )
      {
        LODWORD(v2) = WaitForSingleObject(v5, 0xFFFFFFFF);
        if ( (_DWORD)v2 == -1 )
          LODWORD(v2) = GetLastError();
      }
    }
  }
  v6 = *(void **)(a1 + 88);
  if ( v6 != (void *)-1LL )
  {
    *(_QWORD *)(a1 + 88) = -1;
    LODWORD(v2) = CloseHandle(v6);
  }
  v7 = *(_QWORD *)(a1 + 72);
  if ( v7 )
  {
    LOBYTE(a2) = v7 != a1 + 16;
    LODWORD(v2) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, a2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v8 = *(void **)(a1 + 8);
  if ( v8 )
  {
    LODWORD(v2) = CloseHandle(v8);
    *(_QWORD *)(a1 + 8) = 0;
  }
  return (int)v2;
}

```

## disassembly

```asm
0x140002028  mov     [rsp+arg_0], rbx
0x14000202d  push    rdi
0x14000202e  sub     rsp, 20h
0x140002032  lea     rax, ??_7?$HubTask@J$0A@@DiagHubCommon@@6B@; const DiagHubCommon::HubTask<long,0>::`vftable'
0x140002039  mov     rbx, rcx
0x14000203c  mov     [rcx], rax
0x14000203f  mov     rcx, [rcx+8]; hHandle
0x140002043  test    rcx, rcx
0x140002046  jz      short loc_14000208D
0x140002048  xor     edx, edx; dwMilliseconds
0x14000204a  call    cs:__imp_WaitForSingleObject
0x140002050  test    eax, eax
0x140002052  jz      short loc_14000208D
0x140002054  cmp     qword ptr [rbx+8], 0
0x140002059  jz      short loc_14000206F
0x14000205b  mov     eax, [rbx+60h]
0x14000205e  shr     eax, 1Fh
0x140002061  test    al, al
0x140002063  jnz     short loc_14000206F
0x140002065  mov     rcx, [rbx+58h]; hEvent
0x140002069  call    cs:__imp_SetEvent
0x14000206f  mov     rcx, [rbx+8]; hHandle
0x140002073  test    rcx, rcx
0x140002076  jz      short loc_14000208D
0x140002078  or      edi, 0FFFFFFFFh
0x14000207b  mov     edx, edi; dwMilliseconds
0x14000207d  call    cs:__imp_WaitForSingleObject
0x140002083  cmp     eax, edi
0x140002085  jnz     short loc_14000208D
0x140002087  call    cs:__imp_GetLastError
0x14000208d  mov     rcx, [rbx+58h]; hObject
0x140002091  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140002095  jz      short loc_1400020A5
0x140002097  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14000209f  call    cs:__imp_CloseHandle
0x1400020a5  lea     rdi, [rbx+10h]
0x1400020a9  mov     rcx, [rdi+38h]
0x1400020ad  test    rcx, rcx
0x1400020b0  jz      short loc_1400020CD
0x1400020b2  mov     rax, [rcx]
0x1400020b5  cmp     rcx, rdi
0x1400020b8  setnz   dl
0x1400020bb  mov     rax, [rax+20h]
0x1400020bf  call    cs:__guard_dispatch_icall_fptr
0x1400020c5  mov     qword ptr [rdi+38h], 0
0x1400020cd  mov     rcx, [rbx+8]; hObject
0x1400020d1  test    rcx, rcx
0x1400020d4  jz      short loc_1400020E4
0x1400020d6  call    cs:__imp_CloseHandle
0x1400020dc  mov     qword ptr [rbx+8], 0
0x1400020e4  mov     rbx, [rsp+28h+arg_0]
0x1400020e9  add     rsp, 20h
0x1400020ed  pop     rdi
0x1400020ee  retn
```

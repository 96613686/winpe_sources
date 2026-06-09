# DownloadTaskManager::GetLaunchedTileJobs(uint *,_GUID * *)

- ea: `0x1800c0a00`
- end: `0x1800c0b03`
- name: `?GetLaunchedTileJobs@DownloadTaskManager@@UEAAJPEAIPEAPEAU_GUID@@@Z`
- size: `259`
- prototype: `int(DownloadTaskManager *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002ee38`
- `0x1800af0a4`
- `0x1800c0a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c0acf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c0acf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c0aa6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c0aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0aec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0aec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0a2c`

## string_xrefs

- `0x1800c0a3f`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`

## pseudocode

```c
__int64 __fastcall DownloadTaskManager::GetLaunchedTileJobs(
        DownloadTaskManager *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rsi
  __int64 v9; // r14
  int v10; // eax
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a2 = 0;
  *a3 = 0;
  v6 = (struct _GUID *)CoTaskMemAlloc(16LL * *((unsigned int *)this + 8));
  if ( v6 )
  {
    v7 = 0;
    v8 = 0;
    if ( !*((_DWORD *)this + 8) )
      goto LABEL_12;
    do
    {
      v9 = *((_QWORD *)this + 3) + 288 * v8;
      AcquireSRWLockShared((PSRWLOCK)v9);
      v10 = *(_DWORD *)(v9 + 24);
      if ( (v10 & 0x10) != 0 && (v10 & 0xF) == 3 )
      {
        v11 = v7++;
        v6[v11] = *(struct _GUID *)(v9 + 8);
      }
      ReleaseSRWLockShared((PSRWLOCK)v9);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *((_DWORD *)this + 8) );
    if ( v7 )
    {
      *a3 = v6;
      *a2 = v7;
    }
    else
    {
LABEL_12:
      CoTaskMemFree(v6);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x87D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)0x8007000ELL,
      v13);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids, 2147942414LL);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c0a00  push    rbx
0x1800c0a02  push    rbp
0x1800c0a03  push    rsi
0x1800c0a04  push    rdi
0x1800c0a05  push    r12
0x1800c0a07  push    r14
0x1800c0a09  push    r15; int
0x1800c0a0b  sub     rsp, 20h
0x1800c0a0f  mov     dword ptr [rdx], 0
0x1800c0a15  mov     rbp, rcx
0x1800c0a18  mov     qword ptr [r8], 0
0x1800c0a1f  mov     r15, r8
0x1800c0a22  mov     ecx, [rcx+20h]
0x1800c0a25  mov     r12, rdx
0x1800c0a28  shl     rcx, 4; cb
0x1800c0a2c  call    cs:__imp_CoTaskMemAlloc
0x1800c0a32  mov     rdi, rax
0x1800c0a35  test    rax, rax
0x1800c0a38  jnz     short loc_1800C0A8E
0x1800c0a3a  mov     rcx, [rsp+58h]; this
0x1800c0a3f  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c0a46  mov     r9d, 8007000Eh; char *
0x1800c0a4c  mov     edx, 87Dh; void *
0x1800c0a51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c0a56  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0a5d  lea     rax, WPP_GLOBAL_Control
0x1800c0a64  cmp     rcx, rax
0x1800c0a67  jz      loc_1800C0AF2
0x1800c0a6d  test    byte ptr [rcx+1Ch], 80h
0x1800c0a71  jz      short loc_1800C0AF2
0x1800c0a73  mov     rcx, [rcx+10h]
0x1800c0a77  lea     edx, [rdi+3Ah]
0x1800c0a7a  mov     r9d, 8007000Eh
0x1800c0a80  lea     r8, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids
0x1800c0a87  call    WPP_SF_d
0x1800c0a8c  jmp     short loc_1800C0AF2
0x1800c0a8e  xor     ebx, ebx
0x1800c0a90  xor     esi, esi
0x1800c0a92  cmp     [rbp+20h], ebx
0x1800c0a95  jbe     short loc_1800C0AE9
0x1800c0a97  lea     r14, [rsi+rsi*8]
0x1800c0a9b  shl     r14, 5
0x1800c0a9f  add     r14, [rbp+18h]
0x1800c0aa3  mov     rcx, r14; SRWLock
0x1800c0aa6  call    cs:__imp_AcquireSRWLockShared
0x1800c0aac  mov     eax, [r14+18h]
0x1800c0ab0  test    al, 10h
0x1800c0ab2  jz      short loc_1800C0ACC
0x1800c0ab4  and     eax, 0Fh
0x1800c0ab7  cmp     al, 3
0x1800c0ab9  jnz     short loc_1800C0ACC
0x1800c0abb  movups  xmm0, xmmword ptr [r14+8]
0x1800c0ac0  mov     eax, ebx
0x1800c0ac2  add     rax, rax
0x1800c0ac5  inc     ebx
0x1800c0ac7  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x1800c0acc  mov     rcx, r14; SRWLock
0x1800c0acf  call    cs:__imp_ReleaseSRWLockShared
0x1800c0ad5  inc     esi
0x1800c0ad7  cmp     esi, [rbp+20h]
0x1800c0ada  jb      short loc_1800C0A97
0x1800c0adc  test    ebx, ebx
0x1800c0ade  jz      short loc_1800C0AE9
0x1800c0ae0  mov     [r15], rdi
0x1800c0ae3  mov     [r12], ebx
0x1800c0ae7  jmp     short loc_1800C0AF2
0x1800c0ae9  mov     rcx, rdi; pv
0x1800c0aec  call    cs:__imp_CoTaskMemFree
0x1800c0af2  xor     eax, eax
0x1800c0af4  add     rsp, 20h
0x1800c0af8  pop     r15
0x1800c0afa  pop     r14
0x1800c0afc  pop     r12
0x1800c0afe  pop     rdi
0x1800c0aff  pop     rsi
0x1800c0b00  pop     rbp
0x1800c0b01  pop     rbx
0x1800c0b02  retn
```

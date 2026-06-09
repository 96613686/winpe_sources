# CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x140051f44`
- end: `0x140052081`
- name: `?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z`
- size: `317`
- prototype: `void *(struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000bb38`
- `0x140030038`
- `0x1400300f4`
- `0x1400347cc`
- `0x1400354cc`
- `0x140044164`
- `0x140059f9c`
- `0x14005d6b8`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140051f44`
- `0x140052fb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140051fd0`
- `KERNEL32!GetLastError` at `0x14005201e`
- `KERNEL32!GetLastError` at `0x140051fd0`
- `KERNEL32!GetLastError` at `0x14005201e`
- `KERNEL32!SetLastError` at `0x140052061`
- `KERNEL32!SetLastError` at `0x140052061`
- `KERNEL32!EnterCriticalSection` at `0x140051f94`
- `KERNEL32!EnterCriticalSection` at `0x140051f94`
- `KERNEL32!LeaveCriticalSection` at `0x14005204e`
- `KERNEL32!LeaveCriticalSection` at `0x14005204e`
- `KERNEL32!CreateThread` at `0x140051fbc`
- `KERNEL32!CreateThread` at `0x140051fbc`

## pseudocode

```c
HANDLE __fastcall CreateThreadAndRefCount(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4,
        unsigned int a5,
        unsigned int *lpThreadId)
{
  HANDLE Thread; // rdi
  DWORD LastError; // eax
  DWORD v10; // ebx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
  }
  EnterCriticalSection(&g_CsServiceThreads);
  Thread = CreateThread(0, 0, a3, a4, 0, lpThreadId);
  if ( Thread )
  {
    v10 = 0;
    if ( !(unsigned int)IncreaseServiceThreadsCount()
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      v12 = 50;
      goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 49;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, LastError);
    }
  }
  LeaveCriticalSection(&g_CsServiceThreads);
  if ( !Thread )
    SetLastError(v10);
  return Thread;
}

```

## disassembly

```asm
0x140051f44  mov     [rsp+arg_0], rbx
0x140051f49  mov     [rsp+arg_8], rbp
0x140051f4e  push    rdi
0x140051f4f  sub     rsp, 30h
0x140051f53  mov     rbx, r9
0x140051f56  mov     rdi, r8
0x140051f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f60  lea     rbp, WPP_GLOBAL_Control
0x140051f67  cmp     rcx, rbp
0x140051f6a  jz      short loc_140051F8D
0x140051f6c  test    byte ptr [rcx+1Ch], 4
0x140051f70  jz      short loc_140051F8D
0x140051f72  cmp     byte ptr [rcx+19h], 5
0x140051f76  jb      short loc_140051F8D
0x140051f78  mov     rcx, [rcx+10h]
0x140051f7c  lea     r8, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x140051f83  mov     edx, 30h ; '0'
0x140051f88  call    WPP_SF_
0x140051f8d  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140051f94  call    cs:__imp_EnterCriticalSection
0x140051f9b  nop     dword ptr [rax+rax+00h]
0x140051fa0  mov     rax, [rsp+38h+arg_28]
0x140051fa5  mov     r9, rbx; lpParameter
0x140051fa8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140051fad  mov     r8, rdi; lpStartAddress
0x140051fb0  xor     edx, edx; dwStackSize
0x140051fb2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140051fba  xor     ecx, ecx; lpThreadAttributes
0x140051fbc  call    cs:__imp_CreateThread
0x140051fc3  nop     dword ptr [rax+rax+00h]
0x140051fc8  mov     rdi, rax
0x140051fcb  test    rax, rax
0x140051fce  jnz     short loc_140051FFB
0x140051fd0  call    cs:__imp_GetLastError
0x140051fd7  nop     dword ptr [rax+rax+00h]
0x140051fdc  mov     ebx, eax
0x140051fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140051fe5  cmp     rcx, rbp
0x140051fe8  jz      short loc_140052047
0x140051fea  test    byte ptr [rcx+1Ch], 4
0x140051fee  jz      short loc_140052047
0x140051ff0  cmp     byte ptr [rcx+19h], 2
0x140051ff4  jb      short loc_140052047
0x140051ff6  lea     edx, [rdi+31h]
0x140051ff9  jmp     short loc_140052034
0x140051ffb  xor     ebx, ebx
0x140051ffd  call    ?IncreaseServiceThreadsCount@@YAHXZ; IncreaseServiceThreadsCount(void)
0x140052002  test    eax, eax
0x140052004  jnz     short loc_140052047
0x140052006  mov     rax, cs:WPP_GLOBAL_Control
0x14005200d  cmp     rax, rbp
0x140052010  jz      short loc_140052047
0x140052012  test    byte ptr [rax+1Ch], 4
0x140052016  jz      short loc_140052047
0x140052018  cmp     byte ptr [rax+19h], 2
0x14005201c  jb      short loc_140052047
0x14005201e  call    cs:__imp_GetLastError
0x140052025  nop     dword ptr [rax+rax+00h]
0x14005202a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052031  lea     edx, [rbx+32h]
0x140052034  mov     rcx, [rcx+10h]
0x140052038  lea     r8, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x14005203f  mov     r9d, eax
0x140052042  call    WPP_SF_d
0x140052047  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005204e  call    cs:__imp_LeaveCriticalSection
0x140052055  nop     dword ptr [rax+rax+00h]
0x14005205a  test    rdi, rdi
0x14005205d  jnz     short loc_14005206D
0x14005205f  mov     ecx, ebx; dwErrCode
0x140052061  call    cs:__imp_SetLastError
0x140052068  nop     dword ptr [rax+rax+00h]
0x14005206d  mov     rbx, [rsp+38h+arg_0]
0x140052072  mov     rax, rdi
0x140052075  mov     rbp, [rsp+38h+arg_8]
0x14005207a  add     rsp, 30h
0x14005207e  pop     rdi
0x14005207f  retn
```

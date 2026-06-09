# CNotificationMap::Init(void)

- ea: `0x14005d6b8`
- end: `0x14005d818`
- name: `?Init@CNotificationMap@@QEAAKXZ`
- size: `352`
- prototype: `unsigned int __fastcall(CNotificationMap *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004ae64`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140051f44`
- `0x14005d6b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005d73a`
- `KERNEL32!GetLastError` at `0x14005d79c`
- `KERNEL32!GetLastError` at `0x14005d73a`
- `KERNEL32!GetLastError` at `0x14005d79c`
- `KERNEL32!CloseHandle` at `0x14005d7de`
- `KERNEL32!CloseHandle` at `0x14005d7f9`
- `KERNEL32!CloseHandle` at `0x14005d7de`
- `KERNEL32!CloseHandle` at `0x14005d7f9`
- `KERNEL32!InitializeCriticalSection` at `0x14005d706`
- `KERNEL32!InitializeCriticalSection` at `0x14005d706`
- `KERNEL32!CreateIoCompletionPort` at `0x14005d725`
- `KERNEL32!CreateIoCompletionPort` at `0x14005d725`

## pseudocode

```c
__int64 __fastcall CNotificationMap::Init(CNotificationMap *this)
{
  struct CNotificationMap *v1; // rbx
  HANDLE IoCompletionPort; // rax
  __int64 v3; // rdx
  struct _SECURITY_ATTRIBUTES *v4; // rcx
  DWORD v5; // eax
  DWORD v6; // ebx
  __int64 result; // rax
  HANDLE ThreadAndRefCount; // rax
  DWORD LastError; // eax
  DWORD v10; // edi
  unsigned int v11; // [rsp+20h] [rbp-18h]

  v1 = g_pNotificationMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  *((_BYTE *)v1 + 56) = 1;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  *((_QWORD *)v1 + 1) = IoCompletionPort;
  if ( IoCompletionPort )
  {
    ThreadAndRefCount = CreateThreadAndRefCount(
                          v4,
                          v3,
                          (unsigned int (*)(void *))CNotificationMap::ExtNotificationThread,
                          0,
                          v11,
                          0);
    if ( ThreadAndRefCount )
    {
      CloseHandle(ThreadAndRefCount);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, LastError);
      }
      CloseHandle(*((HANDLE *)v1 + 1));
      result = v10;
      *((_QWORD *)v1 + 1) = 0;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v5);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14005d6b8  mov     [rsp+arg_0], rbx
0x14005d6bd  mov     [rsp+arg_8], rbp
0x14005d6c2  push    rdi
0x14005d6c3  sub     rsp, 30h
0x14005d6c7  mov     rbx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005d6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d6d5  lea     rbp, WPP_GLOBAL_Control
0x14005d6dc  cmp     rcx, rbp
0x14005d6df  jz      short loc_14005D702
0x14005d6e1  test    byte ptr [rcx+1Ch], 4
0x14005d6e5  jz      short loc_14005D702
0x14005d6e7  cmp     byte ptr [rcx+19h], 5
0x14005d6eb  jb      short loc_14005D702
0x14005d6ed  mov     rcx, [rcx+10h]
0x14005d6f1  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d6f8  mov     edx, 27h ; '''
0x14005d6fd  call    WPP_SF_
0x14005d702  lea     rcx, [rbx+10h]; lpCriticalSection
0x14005d706  call    cs:__imp_InitializeCriticalSection
0x14005d70d  nop     dword ptr [rax+rax+00h]
0x14005d712  mov     r9d, 1; NumberOfConcurrentThreads
0x14005d718  mov     byte ptr [rbx+38h], 1
0x14005d71c  xor     r8d, r8d; CompletionKey
0x14005d71f  xor     edx, edx; ExistingCompletionPort
0x14005d721  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14005d725  call    cs:__imp_CreateIoCompletionPort
0x14005d72c  nop     dword ptr [rax+rax+00h]
0x14005d731  mov     [rbx+8], rax
0x14005d735  test    rax, rax
0x14005d738  jnz     short loc_14005D77F
0x14005d73a  call    cs:__imp_GetLastError
0x14005d741  nop     dword ptr [rax+rax+00h]
0x14005d746  mov     ebx, eax
0x14005d748  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d74f  cmp     rcx, rbp
0x14005d752  jz      short loc_14005D778
0x14005d754  test    byte ptr [rcx+1Ch], 4
0x14005d758  jz      short loc_14005D778
0x14005d75a  cmp     byte ptr [rcx+19h], 2
0x14005d75e  jb      short loc_14005D778
0x14005d760  mov     rcx, [rcx+10h]
0x14005d764  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d76b  mov     edx, 28h ; '('
0x14005d770  mov     r9d, eax
0x14005d773  call    WPP_SF_d
0x14005d778  mov     eax, ebx
0x14005d77a  jmp     loc_14005D807
0x14005d77f  xor     r9d, r9d; void *
0x14005d782  mov     [rsp+38h+var_10], 0; unsigned int *
0x14005d78b  lea     r8, ?ExtNotificationThread@CNotificationMap@@CAKPEAX@Z; unsigned int (*)(void *)
0x14005d792  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14005d797  test    rax, rax
0x14005d79a  jnz     short loc_14005D7F6
0x14005d79c  call    cs:__imp_GetLastError
0x14005d7a3  nop     dword ptr [rax+rax+00h]
0x14005d7a8  mov     edi, eax
0x14005d7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d7b1  cmp     rcx, rbp
0x14005d7b4  jz      short loc_14005D7DA
0x14005d7b6  test    byte ptr [rcx+1Ch], 4
0x14005d7ba  jz      short loc_14005D7DA
0x14005d7bc  cmp     byte ptr [rcx+19h], 2
0x14005d7c0  jb      short loc_14005D7DA
0x14005d7c2  mov     rcx, [rcx+10h]
0x14005d7c6  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005d7cd  mov     edx, 29h ; ')'
0x14005d7d2  mov     r9d, eax
0x14005d7d5  call    WPP_SF_d
0x14005d7da  mov     rcx, [rbx+8]; hObject
0x14005d7de  call    cs:__imp_CloseHandle
0x14005d7e5  nop     dword ptr [rax+rax+00h]
0x14005d7ea  mov     eax, edi
0x14005d7ec  mov     qword ptr [rbx+8], 0
0x14005d7f4  jmp     short loc_14005D807
0x14005d7f6  mov     rcx, rax; hObject
0x14005d7f9  call    cs:__imp_CloseHandle
0x14005d800  nop     dword ptr [rax+rax+00h]
0x14005d805  xor     eax, eax
0x14005d807  mov     rbx, [rsp+38h+arg_0]
0x14005d80c  mov     rbp, [rsp+38h+arg_8]
0x14005d811  add     rsp, 30h
0x14005d815  pop     rdi
0x14005d816  retn
```

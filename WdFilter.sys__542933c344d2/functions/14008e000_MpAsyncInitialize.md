# MpAsyncInitialize

- ea: `0x14008e000`
- end: `0x14008e2f0`
- name: `MpAsyncInitialize`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x140003ed0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140079540`
- `0x14008e000`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14008e2b3`
- `ntoskrnl!ZwClose` at `0x140094a6e`
- `ntoskrnl!ZwClose` at `0x14008e2b3`
- `ntoskrnl!ZwClose` at `0x140094a6e`
- `ntoskrnl!KeInitializeEvent` at `0x14008e0ed`
- `ntoskrnl!KeInitializeEvent` at `0x14008e109`
- `ntoskrnl!KeInitializeEvent` at `0x14008e0ed`
- `ntoskrnl!KeInitializeEvent` at `0x14008e109`
- `ntoskrnl!PsThreadType` at `0x14008e25f`
- `ntoskrnl!KeInitializeSemaphore` at `0x14008e128`
- `ntoskrnl!KeInitializeSemaphore` at `0x14008e128`
- `ntoskrnl!PsCreateSystemThread` at `0x14008e1e5`
- `ntoskrnl!PsCreateSystemThread` at `0x14008e1e5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008e161`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008e199`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008e161`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008e199`

## pseudocode

```c
__int64 MpAsyncInitialize()
{
  _DWORD *PoolWithTag; // rax
  _DWORD *v1; // rcx
  NTSTATUS v2; // ebx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  void *ThreadHandle; // [rsp+48h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-48h] BYREF

  memset(&ObjectAttributes, 0, 44);
  ThreadHandle = 0;
  PoolWithTag = (_DWORD *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 512, 1684099149);
  v1 = PoolWithTag;
  MpAsync = PoolWithTag;
  if ( !PoolWithTag )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
        KeGetCurrentThread());
    v2 = -1073741670;
    goto LABEL_16;
  }
  *PoolWithTag = 33610247;
  v3 = PoolWithTag + 2;
  v3[1] = v3;
  *v3 = v3;
  *((_QWORD *)v1 + 4) = v1 + 6;
  *((_QWORD *)v1 + 3) = v1 + 6;
  v1[26] = 1;
  *((_QWORD *)v1 + 14) = 0;
  v1[30] = 0;
  KeInitializeEvent((PRKEVENT)(v1 + 32), SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)MpAsync + 2, NotificationEvent, 0);
  KeInitializeSemaphore((PRKSEMAPHORE)((char *)MpAsync + 72), 0, 0x7FFFFFFF);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpAsync + 192), 0, 0, 0, 0x30u, 0x6E61504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpAsync + 3, 0, 0, 0, 0x800u, 0x676C504Du, 0);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, MpAsyncpWorkerThread, 0);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_16;
    v4 = 11;
LABEL_10:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
      KeGetCurrentThread(),
      v2);
    goto LABEL_16;
  }
  v2 = MpReferenceObjectByHandle((int)ThreadHandle, 0x1FFFFF, (int)PsThreadType, 0, (PVOID *)MpAsync + 5);
  if ( v2 >= 0 )
  {
    v2 = 0;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v4 = 12;
    goto LABEL_10;
  }
LABEL_16:
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  if ( v2 < 0 )
    MpAsyncShutdown();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14008e000  mov     r11, rsp
0x14008e003  mov     [r11+8], rbx
0x14008e007  mov     [r11+10h], rsi
0x14008e00b  push    rdi
0x14008e00c  sub     rsp, 90h
0x14008e013  mov     rax, cs:__security_cookie
0x14008e01a  xor     rax, rsp
0x14008e01d  mov     [rsp+98h+var_18], rax
0x14008e025  mov     [rsp+98h+var_58], 0C0000001h
0x14008e02d  xor     eax, eax
0x14008e02f  xorps   xmm0, xmm0
0x14008e032  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x14008e037  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x14008e03c  mov     [r11-28h], rax
0x14008e040  mov     dword ptr [rsp+98h+ObjectAttributes.SecurityQualityOfService], eax
0x14008e044  xor     edi, edi
0x14008e046  mov     [r11-50h], rdi
0x14008e04a  mov     esi, 200h
0x14008e04f  mov     r8d, 6461504Dh
0x14008e055  mov     edx, esi
0x14008e057  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14008e05d  call    MpAllocatePoolWithTag
0x14008e062  mov     rcx, rax
0x14008e065  mov     cs:MpAsync, rax
0x14008e06c  test    rax, rax
0x14008e06f  jnz     short loc_14008E0B8
0x14008e071  lea     rax, WPP_GLOBAL_Control
0x14008e078  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e07f  cmp     rcx, rax
0x14008e082  jz      short loc_14008E0AE
0x14008e084  mov     eax, [rcx+2Ch]
0x14008e087  test    al, 1
0x14008e089  jz      short loc_14008E0AE
0x14008e08b  mov     r9, gs:188h
0x14008e094  lea     edx, [rdi+0Ah]
0x14008e097  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x14008e09e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e0a5  mov     rcx, [rcx+18h]
0x14008e0a9  call    WPP_SF_q
0x14008e0ae  mov     ebx, 0C000009Ah
0x14008e0b3  jmp     loc_14008E2A5
0x14008e0b8  mov     dword ptr [rax], 200DA07h
0x14008e0be  add     rax, 8
0x14008e0c2  mov     [rax+8], rax
0x14008e0c6  mov     [rax], rax
0x14008e0c9  lea     rax, [rcx+18h]
0x14008e0cd  mov     [rax+8], rax
0x14008e0d1  mov     [rax], rax
0x14008e0d4  mov     dword ptr [rcx+68h], 1
0x14008e0db  mov     [rcx+70h], rdi
0x14008e0df  mov     [rcx+78h], edi
0x14008e0e2  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x14008e0e6  xor     r8d, r8d; State
0x14008e0e9  lea     edx, [r8+1]; Type
0x14008e0ed  call    cs:__imp_KeInitializeEvent
0x14008e0f4  nop     dword ptr [rax+rax+00h]
0x14008e0f9  mov     rcx, cs:MpAsync
0x14008e100  add     rcx, 30h ; '0'; Event
0x14008e104  xor     r8d, r8d; State
0x14008e107  xor     edx, edx; Type
0x14008e109  call    cs:__imp_KeInitializeEvent
0x14008e110  nop     dword ptr [rax+rax+00h]
0x14008e115  mov     rcx, cs:MpAsync
0x14008e11c  add     rcx, 48h ; 'H'; Semaphore
0x14008e120  xor     edx, edx; Count
0x14008e122  mov     r8d, 7FFFFFFFh; Limit
0x14008e128  call    cs:__imp_KeInitializeSemaphore
0x14008e12f  nop     dword ptr [rax+rax+00h]
0x14008e134  mov     rcx, cs:MpAsync
0x14008e13b  add     rcx, 0C0h; Lookaside
0x14008e142  mov     [rsp+98h+Depth], di; Depth
0x14008e147  mov     [rsp+98h+Tag], 6E61504Dh; Tag
0x14008e14f  mov     ebx, 30h ; '0'
0x14008e154  mov     [rsp+98h+Size], rbx; Size
0x14008e159  xor     r9d, r9d; Flags
0x14008e15c  xor     r8d, r8d; Free
0x14008e15f  xor     edx, edx; Allocate
0x14008e161  call    cs:__imp_ExInitializePagedLookasideList
0x14008e168  nop     dword ptr [rax+rax+00h]
0x14008e16d  mov     rcx, cs:MpAsync
0x14008e174  add     rcx, 180h; Lookaside
0x14008e17b  mov     [rsp+98h+Depth], di; Depth
0x14008e180  mov     [rsp+98h+Tag], 676C504Dh; Tag
0x14008e188  mov     [rsp+98h+Size], 800h; Size
0x14008e191  xor     r9d, r9d; Flags
0x14008e194  xor     r8d, r8d; Free
0x14008e197  xor     edx, edx; Allocate
0x14008e199  call    cs:__imp_ExInitializePagedLookasideList
0x14008e1a0  nop     dword ptr [rax+rax+00h]
0x14008e1a5  mov     [rsp+98h+ObjectAttributes.Length], ebx
0x14008e1a9  mov     [rsp+98h+ObjectAttributes.RootDirectory], rdi
0x14008e1ae  mov     [rsp+98h+ObjectAttributes.Attributes], esi
0x14008e1b2  mov     [rsp+98h+ObjectAttributes.ObjectName], rdi
0x14008e1b7  xorps   xmm0, xmm0
0x14008e1ba  movdqu  xmmword ptr [rsp+70h], xmm0
0x14008e1c0  mov     qword ptr [rsp+98h+Depth], rdi; StartContext
0x14008e1c5  lea     rax, MpAsyncpWorkerThread
0x14008e1cc  mov     qword ptr [rsp+98h+Tag], rax; StartRoutine
0x14008e1d1  mov     [rsp+98h+Size], rdi; ClientId
0x14008e1d6  xor     r9d, r9d; ProcessHandle
0x14008e1d9  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x14008e1de  xor     edx, edx; DesiredAccess
0x14008e1e0  lea     rcx, [rsp+98h+ThreadHandle]; ThreadHandle
0x14008e1e5  call    cs:__imp_PsCreateSystemThread
0x14008e1ec  nop     dword ptr [rax+rax+00h]
0x14008e1f1  mov     ebx, eax
0x14008e1f3  mov     [rsp+98h+var_58], eax
0x14008e1f7  test    eax, eax
0x14008e1f9  jns     short loc_14008E24C
0x14008e1fb  lea     rax, WPP_GLOBAL_Control
0x14008e202  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e209  cmp     rcx, rax
0x14008e20c  jz      loc_14008E2A9
0x14008e212  mov     ecx, [rcx+2Ch]
0x14008e215  test    cl, 1
0x14008e218  jz      loc_14008E2A9
0x14008e21e  mov     edx, 0Bh
0x14008e223  lfence
0x14008e226  mov     r9, gs:188h
0x14008e22f  mov     dword ptr [rsp+98h+Size], ebx
0x14008e233  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x14008e23a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e241  mov     rcx, [rcx+18h]
0x14008e245  call    WPP_SF_qD
0x14008e24a  jmp     short loc_14008E2A9
0x14008e24c  mov     rax, cs:MpAsync
0x14008e253  add     rax, 28h ; '('
0x14008e257  mov     [rsp+98h+Size], rax; PVOID *
0x14008e25c  xor     r9d, r9d; int
0x14008e25f  mov     r8, cs:__imp_PsThreadType
0x14008e266  mov     r8, [r8]; int
0x14008e269  mov     edx, 1FFFFFh; int
0x14008e26e  mov     rcx, [rsp+98h+ThreadHandle]; int
0x14008e273  call    MpReferenceObjectByHandle
0x14008e278  mov     ebx, eax
0x14008e27a  mov     [rsp+98h+var_58], eax
0x14008e27e  test    eax, eax
0x14008e280  jns     short loc_14008E2A3
0x14008e282  lea     rax, WPP_GLOBAL_Control
0x14008e289  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e290  cmp     rcx, rax
0x14008e293  jz      short loc_14008E2A9
0x14008e295  mov     eax, [rcx+2Ch]
0x14008e298  test    al, 1
0x14008e29a  jz      short loc_14008E2A9
0x14008e29c  mov     edx, 0Ch
0x14008e2a1  jmp     short loc_14008E223
0x14008e2a3  mov     ebx, edi
0x14008e2a5  mov     [rsp+98h+var_58], ebx
0x14008e2a9  mov     rcx, [rsp+98h+ThreadHandle]; Handle
0x14008e2ae  test    rcx, rcx
0x14008e2b1  jz      short loc_14008E2BF
0x14008e2b3  call    cs:__imp_ZwClose
0x14008e2ba  nop     dword ptr [rax+rax+00h]
0x14008e2bf  test    ebx, ebx
0x14008e2c1  jns     short loc_14008E2C8
0x14008e2c3  call    MpAsyncShutdown
0x14008e2c8  mov     eax, ebx
0x14008e2ca  mov     rcx, [rsp+98h+var_18]
0x14008e2d2  xor     rcx, rsp; StackCookie
0x14008e2d5  call    __security_check_cookie
0x14008e2da  lea     r11, [rsp+98h+var_8]
0x14008e2e2  mov     rbx, [r11+10h]
0x14008e2e6  mov     rsi, [r11+18h]
0x14008e2ea  mov     rsp, r11
0x14008e2ed  pop     rdi
0x14008e2ee  retn
0x140094a5c  push    rbp
0x140094a5e  sub     rsp, 40h
0x140094a62  mov     rbp, rdx
0x140094a65  mov     rcx, [rbp+48h]; Handle
0x140094a69  test    rcx, rcx
0x140094a6c  jz      short loc_140094A7B
0x140094a6e  call    cs:__imp_ZwClose
0x140094a75  nop     dword ptr [rax+rax+00h]
0x140094a7a  nop
0x140094a7b  cmp     dword ptr [rbp+40h], 0
0x140094a7f  jge     short loc_140094A87
0x140094a81  call    MpAsyncShutdown
0x140094a86  nop
0x140094a87  add     rsp, 40h
0x140094a8b  pop     rbp
0x140094a8c  retn
```

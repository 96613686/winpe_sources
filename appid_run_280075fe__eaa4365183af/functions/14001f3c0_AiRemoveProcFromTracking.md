# AiRemoveProcFromTracking

- ea: `0x14001f3c0`
- end: `0x14001f8f0`
- name: `AiRemoveProcFromTracking`
- size: `1328`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140036f60`

## callees

- `0x140001bbc`
- `0x140006b20`
- `0x14001f310`
- `0x14001f3c0`
- `0x140020db4`
- `0x1400354d0`
- `0x140035530`
- `0x140036930`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001f532`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f5e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f63e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f6af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f85b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f532`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f5e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f63e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f6af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f85b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f560`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f658`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f6ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f560`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f658`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f6ed`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14001f4e7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14001f4e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f867`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f6c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f8d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f6c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f8d8`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14001f447`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14001f447`
- `ntoskrnl!ZwOpenProcess` at `0x14001f425`
- `ntoskrnl!ZwOpenProcess` at `0x14001f425`
- `ntoskrnl!ZwClose` at `0x14001f45e`
- `ntoskrnl!ZwClose` at `0x14001f492`
- `ntoskrnl!ZwClose` at `0x14001f45e`
- `ntoskrnl!ZwClose` at `0x14001f492`

## pseudocode

```c
void __fastcall AiRemoveProcFromTracking(struct _DEVICE_OBJECT *a1, void *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rdi
  void *v5; // rcx
  int IsTokenSandBoxed; // ebx
  struct _DEVICE_OBJECT **DpcData; // rbx
  struct _DEVICE_OBJECT *v8; // rax
  struct _DEVICE_OBJECT *v9; // rax
  struct _DRIVER_OBJECT *v10; // rcx
  PVOID *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  _QWORD *v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  struct _LIST_ENTRY *Flink; // rdi
  struct _DEVICE_OBJECT *v20; // rcx
  struct _DEVICE_OBJECT *AttachedDevice; // r8
  struct _DEVICE_OBJECT *v22; // rbx
  unsigned __int64 v23; // rdx
  struct _DRIVER_OBJECT *DriverObject; // rax
  struct _LIST_ENTRY *i; // rsi
  struct _LIST_ENTRY *v26; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _DEVICE_OBJECT *v28; // rcx
  __int64 v29; // rax
  struct _DRIVER_OBJECT *v30; // rdx
  void *ProcessHandle; // [rsp+20h] [rbp-49h] BYREF
  PVOID P; // [rsp+28h] [rbp-41h] BYREF
  PVOID *p_P; // [rsp+30h] [rbp-39h]
  __int128 Buf1; // [rsp+38h] [rbp-31h] BYREF
  _CLIENT_ID ClientId; // [rsp+48h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  char v37; // [rsp+D8h] [rbp+6Fh] BYREF
  int v38; // [rsp+E0h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  ClientId.UniqueProcess = a2;
  v38 = 0;
  v37 = 0;
  TokenHandle = 0;
  ProcessHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  Buf1 = 0;
  ClientId.UniqueThread = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  v3 = ZwOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( v3 >= 0 )
    v3 = ZwOpenProcessTokenEx(ProcessHandle, 0, 0x200u, &TokenHandle);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( v3 < 0 )
  {
    v5 = TokenHandle;
    v4 = 0;
  }
  else
  {
    v4 = TokenHandle;
    v5 = 0;
    TokenHandle = 0;
    v3 = 0;
  }
  if ( v5 )
    ZwClose(v5);
  if ( v3 >= 0 )
  {
    IsTokenSandBoxed = AiIsTokenSandBoxed(v4, &v37);
    AiCleanTokens(v4, 0);
    if ( IsTokenSandBoxed >= 0 && !v37 )
    {
      ExEnterCriticalRegionAndAcquireResourceShared((PERESOURCE)&WPP_MAIN_CB.Reserved);
      DpcData = (struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.DpcData;
      if ( WPP_MAIN_CB.Dpc.DpcData == &WPP_MAIN_CB.Dpc.DpcData )
        goto LABEL_34;
      if ( a1 == *((struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.DpcData + 2) )
        goto LABEL_18;
      do
      {
        v8 = *DpcData;
        if ( *DpcData == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcData )
          break;
        DpcData = (struct _DEVICE_OBJECT **)*DpcData;
      }
      while ( a1 != v8->NextDevice );
      if ( a1 == DpcData[2] )
      {
LABEL_18:
        ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
        if ( DpcData )
        {
          p_P = &P;
          P = &P;
          ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.Reserved, 1u);
          do
          {
            v9 = *DpcData;
            if ( a1 == DpcData[2] )
            {
              if ( (struct _DEVICE_OBJECT **)v9->DriverObject != DpcData )
                goto LABEL_78;
              v10 = (struct _DRIVER_OBJECT *)DpcData[1];
              if ( *(struct _DEVICE_OBJECT ***)&v10->Type != DpcData )
                goto LABEL_78;
              *(_QWORD *)&v10->Type = v9;
              v9->DriverObject = v10;
              v11 = p_P;
              if ( *p_P != &P )
                goto LABEL_78;
              DpcData[1] = (struct _DEVICE_OBJECT *)p_P;
              *DpcData = (struct _DEVICE_OBJECT *)&P;
              *v11 = DpcData;
              p_P = (PVOID *)DpcData;
            }
            DpcData = (struct _DEVICE_OBJECT **)v9;
          }
          while ( v9 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcData );
          if ( WPP_MAIN_CB.Dpc.DpcData == &WPP_MAIN_CB.Dpc.DpcData && (_QWORD)xmmword_1400198E8 )
            _InterlockedExchange64((volatile __int64 *)&xmmword_1400198E8, 0);
          ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
          v12 = P;
          while ( 1 )
          {
            v13 = *v12;
            if ( *(_QWORD **)(*v12 + 8LL) != v12 )
              break;
            v14 = (_QWORD *)v12[1];
            if ( (_QWORD *)*v14 != v12 )
              break;
            *v14 = v13;
            *(_QWORD *)(v13 + 8) = v14;
            AiReleaseOriginProcessData(v12);
            v12 = P;
            if ( P == &P )
              goto LABEL_41;
          }
LABEL_78:
          __fastfail(3u);
        }
      }
      else
      {
LABEL_34:
        v15 = (_QWORD *)AipIsInSearchListLocked(a1);
        ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
        if ( v15 )
        {
          ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.Reserved, 1u);
          v16 = *v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_78;
          v17 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v17 != v15 )
            goto LABEL_78;
          *v17 = v16;
          *(_QWORD *)(v16 + 8) = v17;
          if ( (_QWORD)xmmword_1400198E8 && WPP_MAIN_CB.SecurityDescriptor == &WPP_MAIN_CB.SecurityDescriptor )
            _InterlockedExchange64((volatile __int64 *)&xmmword_1400198E8, 0);
          ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
          ExFreePoolWithTag(v15, 0);
        }
      }
LABEL_41:
      if ( (unsigned int)SmartlockerGetSubSessionID(a1, &Buf1, &v38) )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.Reserved, 1u);
        Flink = WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink;
        if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink != &WPP_MAIN_CB.DeviceLock.Header.WaitListHead )
        {
          if ( v38 )
          {
            if ( !memcmp(&Buf1, &WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink[2].Flink[2], 0x10u) )
            {
LABEL_47:
              if ( HIDWORD(Flink[2].Blink)-- == 1 )
              {
                v20 = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.SectorSize;
                if ( *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.SectorSize != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.SectorSize )
                {
                  do
                  {
                    AttachedDevice = v20->AttachedDevice;
                    v22 = *(struct _DEVICE_OBJECT **)&v20->Type;
                    v23 = Buf1 - (unsigned __int64)AttachedDevice->CurrentIrp;
                    if ( (struct _IRP *)Buf1 == AttachedDevice->CurrentIrp )
                      v23 = *((_QWORD *)&Buf1 + 1) - (unsigned __int64)AttachedDevice->Timer;
                    if ( !v23 )
                    {
                      if ( (struct _DEVICE_OBJECT *)v22->DriverObject != v20 )
                        goto LABEL_78;
                      DriverObject = v20->DriverObject;
                      if ( *(struct _DEVICE_OBJECT **)&DriverObject->Type != v20 )
                        goto LABEL_78;
                      *(_QWORD *)&DriverObject->Type = v22;
                      v22->DriverObject = DriverObject;
                      ExFreePoolWithTag(v20, 0);
                    }
                    v20 = v22;
                  }
                  while ( v22 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.SectorSize );
                }
                for ( i = Flink[3].Flink; i != &Flink[3]; i = i->Flink )
                  AiParseAndTagUninstallerFromUninstallString(i, Flink[2].Flink);
                v26 = Flink->Flink;
                if ( Flink->Flink->Blink != Flink )
                  goto LABEL_78;
                Blink = Flink->Blink;
                if ( Blink->Flink != Flink )
                  goto LABEL_78;
                Blink->Flink = v26;
                v26->Blink = Blink;
                AiReleaseOriginProcessData(Flink);
              }
            }
            else
            {
              while ( 1 )
              {
                Flink = Flink->Flink;
                if ( Flink == &WPP_MAIN_CB.DeviceLock.Header.WaitListHead )
                  break;
                if ( !memcmp(&Buf1, &Flink[2].Flink[2], 0x10u) )
                  goto LABEL_47;
              }
            }
          }
          else
          {
            v28 = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.SectorSize;
            if ( *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.SectorSize != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.SectorSize )
            {
              while ( 1 )
              {
                if ( v28 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.SectorSize )
                  goto LABEL_61;
                v29 = *(_QWORD *)&v28->Type;
                if ( a1 == v28->NextDevice )
                  break;
                v28 = *(struct _DEVICE_OBJECT **)&v28->Type;
              }
              if ( *(struct _DEVICE_OBJECT **)(v29 + 8) != v28 )
                goto LABEL_78;
              v30 = v28->DriverObject;
              if ( *(struct _DEVICE_OBJECT **)&v30->Type != v28 )
                goto LABEL_78;
              *(_QWORD *)&v30->Type = v29;
              *(_QWORD *)(v29 + 8) = v30;
              ExFreePoolWithTag(v28, 0);
            }
          }
LABEL_61:
          if ( *((_QWORD *)&xmmword_1400198E8 + 1)
            && (*(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.SectorSize == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.SectorSize
             || WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink == &WPP_MAIN_CB.DeviceLock.Header.WaitListHead) )
          {
            _InterlockedExchange64((_QWORD *)&xmmword_1400198E8 + 1, 0);
          }
          if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink == &WPP_MAIN_CB.DeviceLock.Header.WaitListHead )
          {
            if ( qword_1400198F8 )
              _InterlockedExchange64(&qword_1400198F8, 0);
          }
        }
        ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
      }
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x14001f3c0  push    rbp
0x14001f3c2  push    rbx
0x14001f3c3  push    rsi
0x14001f3c4  push    r14
0x14001f3c6  lea     rbp, [rsp-3Fh]
0x14001f3cb  sub     rsp, 0A8h
0x14001f3d2  xor     r14d, r14d
0x14001f3d5  mov     [rbp+57h+ClientId.UniqueProcess], rdx
0x14001f3d9  xorps   xmm0, xmm0
0x14001f3dc  mov     [rbp+57h+arg_10], r14d
0x14001f3e0  mov     rsi, rcx
0x14001f3e3  mov     [rbp+57h+arg_8], r14b
0x14001f3e7  mov     edx, 400h; DesiredAccess
0x14001f3ec  mov     [rbp+57h+TokenHandle], r14
0x14001f3f0  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14001f3f4  mov     [rbp+57h+ProcessHandle], r14
0x14001f3f8  lea     r9, [rbp+57h+ClientId]; ClientId
0x14001f3fc  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14001f400  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001f404  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14001f408  movups  [rbp+57h+Buf1], xmm0
0x14001f40c  mov     [rbp+57h+ClientId.UniqueThread], r14
0x14001f410  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f415  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001f41d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14001f425  call    cs:__imp_ZwOpenProcess
0x14001f42c  nop     dword ptr [rax+rax+00h]
0x14001f431  mov     ebx, eax
0x14001f433  test    eax, eax
0x14001f435  js      short loc_14001F455
0x14001f437  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14001f43b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14001f43f  xor     edx, edx; DesiredAccess
0x14001f441  mov     r8d, 200h; HandleAttributes
0x14001f447  call    cs:__imp_ZwOpenProcessTokenEx
0x14001f44e  nop     dword ptr [rax+rax+00h]
0x14001f453  mov     ebx, eax
0x14001f455  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14001f459  test    rcx, rcx
0x14001f45c  jz      short loc_14001F46A
0x14001f45e  call    cs:__imp_ZwClose
0x14001f465  nop     dword ptr [rax+rax+00h]
0x14001f46a  mov     [rsp+0C0h+var_20], rdi
0x14001f472  test    ebx, ebx
0x14001f474  js      short loc_14001F486
0x14001f476  mov     rdi, [rbp+57h+TokenHandle]
0x14001f47a  mov     rcx, r14
0x14001f47d  mov     [rbp+57h+TokenHandle], rcx
0x14001f481  mov     ebx, r14d
0x14001f484  jmp     short loc_14001F48D
0x14001f486  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14001f48a  mov     rdi, r14
0x14001f48d  test    rcx, rcx
0x14001f490  jz      short loc_14001F49E
0x14001f492  call    cs:__imp_ZwClose
0x14001f499  nop     dword ptr [rax+rax+00h]
0x14001f49e  test    ebx, ebx
0x14001f4a0  js      loc_14001F883
0x14001f4a6  lea     rdx, [rbp+57h+arg_8]
0x14001f4aa  mov     rcx, rdi
0x14001f4ad  call    AiIsTokenSandBoxed
0x14001f4b2  xor     edx, edx
0x14001f4b4  mov     rcx, rdi
0x14001f4b7  mov     ebx, eax
0x14001f4b9  call    AiCleanTokens
0x14001f4be  test    ebx, ebx
0x14001f4c0  js      loc_14001F883
0x14001f4c6  cmp     [rbp+57h+arg_8], r14b
0x14001f4ca  jnz     loc_14001F883
0x14001f4d0  mov     [rsp+0C0h+var_28], r12
0x14001f4d8  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f4df  mov     [rsp+0C0h+var_30], r15
0x14001f4e7  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x14001f4ee  nop     dword ptr [rax+rax+00h]
0x14001f4f3  mov     rbx, cs:WPP_MAIN_CB.Dpc.DpcData
0x14001f4fa  lea     rdi, WPP_MAIN_CB.Dpc.DpcData
0x14001f501  cmp     rbx, rdi
0x14001f504  jz      loc_14001F62C
0x14001f50a  cmp     rsi, [rbx+10h]
0x14001f50e  jz      short loc_14001F52B
0x14001f510  mov     rax, [rbx]
0x14001f513  cmp     rax, rdi
0x14001f516  jz      short loc_14001F521
0x14001f518  mov     rbx, rax
0x14001f51b  cmp     rsi, [rax+10h]
0x14001f51f  jnz     short loc_14001F510
0x14001f521  cmp     rsi, [rbx+10h]
0x14001f525  jnz     loc_14001F62C
0x14001f52b  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f532  call    cs:__imp_ExReleaseResourceLite
0x14001f539  nop     dword ptr [rax+rax+00h]
0x14001f53e  test    rbx, rbx
0x14001f541  jz      loc_14001F6CC
0x14001f547  lea     rax, [rbp+57h+P]
0x14001f54b  mov     dl, 1; Wait
0x14001f54d  mov     [rbp+57h+var_90], rax
0x14001f551  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f558  lea     rax, [rbp+57h+P]
0x14001f55c  mov     [rbp+57h+P], rax
0x14001f560  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001f567  nop     dword ptr [rax+rax+00h]
0x14001f56c  mov     rax, [rbx]
0x14001f56f  cmp     rsi, [rbx+10h]
0x14001f573  jnz     short loc_14001F5B6
0x14001f575  cmp     [rax+8], rbx
0x14001f579  jnz     loc_14001F8E9
0x14001f57f  mov     rcx, [rbx+8]
0x14001f583  cmp     [rcx], rbx
0x14001f586  jnz     loc_14001F8E9
0x14001f58c  mov     [rcx], rax
0x14001f58f  lea     rdx, [rbp+57h+P]
0x14001f593  mov     [rax+8], rcx
0x14001f597  mov     rcx, [rbp+57h+var_90]
0x14001f59b  cmp     [rcx], rdx
0x14001f59e  jnz     loc_14001F8E9
0x14001f5a4  mov     [rbx+8], rcx
0x14001f5a8  lea     rdx, [rbp+57h+P]
0x14001f5ac  mov     [rbx], rdx
0x14001f5af  mov     [rcx], rbx
0x14001f5b2  mov     [rbp+57h+var_90], rbx
0x14001f5b6  mov     rbx, rax
0x14001f5b9  cmp     rax, rdi
0x14001f5bc  jnz     short loc_14001F56C
0x14001f5be  cmp     cs:WPP_MAIN_CB.Dpc.DpcData, rdi
0x14001f5c5  jnz     short loc_14001F5DA
0x14001f5c7  cmp     qword ptr cs:xmmword_1400198E8, r14
0x14001f5ce  jz      short loc_14001F5DA
0x14001f5d0  mov     rax, r14
0x14001f5d3  xchg    rax, qword ptr cs:xmmword_1400198E8
0x14001f5da  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f5e1  call    cs:__imp_ExReleaseResourceLite
0x14001f5e8  nop     dword ptr [rax+rax+00h]
0x14001f5ed  mov     rax, [rbp+57h+P]
0x14001f5f1  mov     rdx, [rax]
0x14001f5f4  cmp     [rdx+8], rax
0x14001f5f8  jnz     loc_14001F8E9
0x14001f5fe  mov     rcx, [rax+8]
0x14001f602  cmp     [rcx], rax
0x14001f605  jnz     loc_14001F8E9
0x14001f60b  mov     [rcx], rdx
0x14001f60e  mov     [rdx+8], rcx
0x14001f612  mov     rcx, rax; P
0x14001f615  call    AiReleaseOriginProcessData
0x14001f61a  mov     rax, [rbp+57h+P]
0x14001f61e  lea     rcx, [rbp+57h+P]
0x14001f622  cmp     rax, rcx
0x14001f625  jnz     short loc_14001F5F1
0x14001f627  jmp     loc_14001F6CC
0x14001f62c  mov     rcx, rsi
0x14001f62f  call    AipIsInSearchListLocked
0x14001f634  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f63b  mov     rbx, rax
0x14001f63e  call    cs:__imp_ExReleaseResourceLite
0x14001f645  nop     dword ptr [rax+rax+00h]
0x14001f64a  test    rbx, rbx
0x14001f64d  jz      short loc_14001F6CC
0x14001f64f  mov     dl, 1; Wait
0x14001f651  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f658  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001f65f  nop     dword ptr [rax+rax+00h]
0x14001f664  mov     rcx, [rbx]
0x14001f667  cmp     [rcx+8], rbx
0x14001f66b  jnz     loc_14001F8E9
0x14001f671  mov     rax, [rbx+8]
0x14001f675  cmp     [rax], rbx
0x14001f678  jnz     loc_14001F8E9
0x14001f67e  mov     [rax], rcx
0x14001f681  mov     [rcx+8], rax
0x14001f685  cmp     qword ptr cs:xmmword_1400198E8, r14
0x14001f68c  jz      short loc_14001F6A8
0x14001f68e  lea     rax, WPP_MAIN_CB.SecurityDescriptor
0x14001f695  cmp     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x14001f69c  jnz     short loc_14001F6A8
0x14001f69e  mov     rax, r14
0x14001f6a1  xchg    rax, qword ptr cs:xmmword_1400198E8
0x14001f6a8  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f6af  call    cs:__imp_ExReleaseResourceLite
0x14001f6b6  nop     dword ptr [rax+rax+00h]
0x14001f6bb  xor     edx, edx; Tag
0x14001f6bd  mov     rcx, rbx; P
0x14001f6c0  call    cs:__imp_ExFreePoolWithTag
0x14001f6c7  nop     dword ptr [rax+rax+00h]
0x14001f6cc  lea     r8, [rbp+57h+arg_10]
0x14001f6d0  mov     rcx, rsi
0x14001f6d3  lea     rdx, [rbp+57h+Buf1]
0x14001f6d7  call    SmartlockerGetSubSessionID
0x14001f6dc  test    eax, eax
0x14001f6de  jz      loc_14001F867
0x14001f6e4  mov     dl, 1; Wait
0x14001f6e6  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f6ed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001f6f4  nop     dword ptr [rax+rax+00h]
0x14001f6f9  mov     rdi, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x14001f700  lea     r15, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001f707  cmp     rdi, r15
0x14001f70a  jz      loc_14001F854
0x14001f710  lea     r12, WPP_MAIN_CB.SectorSize
0x14001f717  cmp     [rbp+57h+arg_10], r14d
0x14001f71b  jz      loc_14001F899
0x14001f721  mov     rdx, [rdi+20h]
0x14001f725  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14001f729  add     rdx, 20h ; ' '; Buf2
0x14001f72d  mov     r8d, 10h; Size
0x14001f733  call    memcmp
0x14001f738  test    eax, eax
0x14001f73a  jz      short loc_14001F763
0x14001f73c  mov     rdi, [rdi]
0x14001f73f  cmp     rdi, r15
0x14001f742  jz      loc_14001F813
0x14001f748  mov     rdx, [rdi+20h]
0x14001f74c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14001f750  add     rdx, 20h ; ' '; Buf2
0x14001f754  mov     r8d, 10h; Size
0x14001f75a  call    memcmp
0x14001f75f  test    eax, eax
0x14001f761  jnz     short loc_14001F73C
0x14001f763  sub     dword ptr [rdi+2Ch], 1
0x14001f767  jnz     loc_14001F813
0x14001f76d  mov     rcx, qword ptr cs:WPP_MAIN_CB.SectorSize; P
0x14001f774  cmp     rcx, r12
0x14001f777  jz      short loc_14001F7C9
0x14001f779  mov     r8, [rcx+18h]
0x14001f77d  mov     rdx, qword ptr [rbp+57h+Buf1]
0x14001f781  mov     rbx, [rcx]
0x14001f784  sub     rdx, [r8+20h]
0x14001f788  jnz     short loc_14001F792
0x14001f78a  mov     rdx, qword ptr [rbp+57h+Buf1+8]
0x14001f78e  sub     rdx, [r8+28h]; Tag
0x14001f792  test    rdx, rdx
0x14001f795  jnz     short loc_14001F7C1
0x14001f797  cmp     [rbx+8], rcx
0x14001f79b  jnz     loc_14001F8E9
0x14001f7a1  mov     rax, [rcx+8]
0x14001f7a5  cmp     [rax], rcx
0x14001f7a8  jnz     loc_14001F8E9
0x14001f7ae  mov     [rax], rbx
0x14001f7b1  mov     [rbx+8], rax
0x14001f7b5  call    cs:__imp_ExFreePoolWithTag
0x14001f7bc  nop     dword ptr [rax+rax+00h]
0x14001f7c1  mov     rcx, rbx
0x14001f7c4  cmp     rbx, r12
0x14001f7c7  jnz     short loc_14001F779
0x14001f7c9  mov     rsi, [rdi+30h]
0x14001f7cd  lea     rbx, [rdi+30h]
0x14001f7d1  cmp     rsi, rbx
0x14001f7d4  jz      short loc_14001F7EA
0x14001f7d6  mov     rdx, [rdi+20h]
0x14001f7da  mov     rcx, rsi
0x14001f7dd  call    AiParseAndTagUninstallerFromUninstallString
0x14001f7e2  mov     rsi, [rsi]
0x14001f7e5  cmp     rsi, rbx
0x14001f7e8  jnz     short loc_14001F7D6
0x14001f7ea  mov     rax, [rdi]
0x14001f7ed  cmp     [rax+8], rdi
0x14001f7f1  jnz     loc_14001F8E9
0x14001f7f7  mov     rcx, [rdi+8]
0x14001f7fb  cmp     [rcx], rdi
0x14001f7fe  jnz     loc_14001F8E9
0x14001f804  mov     [rcx], rax
0x14001f807  mov     [rax+8], rcx
0x14001f80b  mov     rcx, rdi; P
0x14001f80e  call    AiReleaseOriginProcessData
0x14001f813  cmp     qword ptr cs:xmmword_1400198E8+8, r14
0x14001f81a  jz      short loc_14001F838
0x14001f81c  cmp     qword ptr cs:WPP_MAIN_CB.SectorSize, r12
0x14001f823  jz      short loc_14001F82E
0x14001f825  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, r15
0x14001f82c  jnz     short loc_14001F838
0x14001f82e  mov     rax, r14
0x14001f831  xchg    rax, qword ptr cs:xmmword_1400198E8+8
0x14001f838  cmp     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, r15
0x14001f83f  jnz     short loc_14001F854
0x14001f841  cmp     cs:qword_1400198F8, r14
0x14001f848  jz      short loc_14001F854
0x14001f84a  mov     rax, r14
0x14001f84d  xchg    rax, cs:qword_1400198F8
0x14001f854  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x14001f85b  call    cs:__imp_ExReleaseResourceLite
0x14001f862  nop     dword ptr [rax+rax+00h]
0x14001f867  call    cs:__imp_KeLeaveCriticalRegion
0x14001f86e  nop     dword ptr [rax+rax+00h]
0x14001f873  mov     r12, [rsp+0C0h+var_28]
0x14001f87b  mov     r15, [rsp+0C0h+var_30]
0x14001f883  mov     rdi, [rsp+0C0h+var_20]
0x14001f88b  add     rsp, 0A8h
0x14001f892  pop     r14
0x14001f894  pop     rsi
0x14001f895  pop     rbx
0x14001f896  pop     rbp
0x14001f897  retn
0x14001f899  mov     rcx, qword ptr cs:WPP_MAIN_CB.SectorSize; P
0x14001f8a0  cmp     rcx, r12
0x14001f8a3  jz      loc_14001F813
0x14001f8a9  cmp     rcx, r12
0x14001f8ac  jz      loc_14001F813
0x14001f8b2  mov     rax, [rcx]
0x14001f8b5  cmp     rsi, [rcx+10h]
0x14001f8b9  jz      short loc_14001F8C0
0x14001f8bb  mov     rcx, rax
0x14001f8be  jmp     short loc_14001F8A9
  ... truncated ...
```

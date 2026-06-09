# BipSaveWorkItemInStore

- ea: `0x180064214`
- end: `0x180064821`
- name: `BipSaveWorkItemInStore`
- size: `1549`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008598`

## callees

- `0x18000214c`
- `0x180005670`
- `0x180010c5c`
- `0x180011e7c`
- `0x180013d20`
- `0x180024724`
- `0x180024b54`
- `0x180025d68`
- `0x180025e0c`
- `0x180025f14`
- `0x180025fcc`
- `0x180026b28`
- `0x180033110`
- `0x18004af00`
- `0x180053100`
- `0x180064214`
- `0x18006d364`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x1800647a4`
- `ntdll!NtDeleteValueKey` at `0x1800647a4`
- `ntdll!RtlAppendUnicodeToString` at `0x1800643bf`
- `ntdll!RtlAppendUnicodeToString` at `0x1800643bf`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180064397`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180064397`
- `ntdll!NtDeleteKey` at `0x1800647db`
- `ntdll!NtDeleteKey` at `0x1800647db`
- `ntdll!RtlFreeUnicodeString` at `0x180064366`
- `ntdll!RtlFreeUnicodeString` at `0x1800647b0`
- `ntdll!RtlFreeUnicodeString` at `0x180064366`
- `ntdll!RtlFreeUnicodeString` at `0x1800647b0`
- `ntdll!RtlStringFromGUID` at `0x180064383`
- `ntdll!RtlStringFromGUID` at `0x180064383`
- `ntdll!RtlInitUnicodeString` at `0x180064262`
- `ntdll!RtlInitUnicodeString` at `0x1800642ca`
- `ntdll!RtlInitUnicodeString` at `0x180064407`
- `ntdll!RtlInitUnicodeString` at `0x18006443a`
- `ntdll!RtlInitUnicodeString` at `0x180064482`
- `ntdll!RtlInitUnicodeString` at `0x1800644b4`
- `ntdll!RtlInitUnicodeString` at `0x180064529`
- `ntdll!RtlInitUnicodeString` at `0x18006453a`
- `ntdll!RtlInitUnicodeString` at `0x180064571`
- `ntdll!RtlInitUnicodeString` at `0x1800645ab`
- `ntdll!RtlInitUnicodeString` at `0x1800645eb`
- `ntdll!RtlInitUnicodeString` at `0x180064645`
- `ntdll!RtlInitUnicodeString` at `0x18006468e`
- `ntdll!RtlInitUnicodeString` at `0x1800646d8`
- `ntdll!RtlInitUnicodeString` at `0x180064262`
- `ntdll!RtlInitUnicodeString` at `0x1800642ca`
- `ntdll!RtlInitUnicodeString` at `0x180064407`
- `ntdll!RtlInitUnicodeString` at `0x18006443a`
- `ntdll!RtlInitUnicodeString` at `0x180064482`
- `ntdll!RtlInitUnicodeString` at `0x1800644b4`
- `ntdll!RtlInitUnicodeString` at `0x180064529`
- `ntdll!RtlInitUnicodeString` at `0x18006453a`
- `ntdll!RtlInitUnicodeString` at `0x180064571`
- `ntdll!RtlInitUnicodeString` at `0x1800645ab`
- `ntdll!RtlInitUnicodeString` at `0x1800645eb`
- `ntdll!RtlInitUnicodeString` at `0x180064645`
- `ntdll!RtlInitUnicodeString` at `0x18006468e`
- `ntdll!RtlInitUnicodeString` at `0x1800646d8`
- `ntdll!RtlFreeHeap` at `0x1800647c8`
- `ntdll!RtlFreeHeap` at `0x1800647fd`
- `ntdll!RtlFreeHeap` at `0x1800647c8`
- `ntdll!RtlFreeHeap` at `0x1800647fd`
- `ntdll!RtlAllocateHeap` at `0x180064328`
- `ntdll!RtlAllocateHeap` at `0x180064328`
- `ntdll!NtClose` at `0x1800647e5`
- `ntdll!NtClose` at `0x1800647e5`

## string_xrefs

- `0x1800645e0`: `TaskEntryPoint`
- `0x180064566`: `TaskEntryPointId`

## pseudocode

```c
__int64 __fastcall BipSaveWorkItemInStore(__int64 a1)
{
  NTSTATUS v2; // ebx
  __int64 v3; // r8
  WCHAR *Heap; // rax
  unsigned int v5; // esi
  __int64 v6; // r14
  const WCHAR *v7; // rdx
  USHORT Length; // ax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // edx
  void *v15; // r8
  ULONG v16; // r9d
  int v17; // r8d
  __int128 *WorkItemId; // rax
  __int128 v19; // xmm1
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  HANDLE v23; // rcx
  HANDLE KeyHandle; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-71h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-61h] BYREF
  int v28; // [rsp+68h] [rbp-51h] BYREF
  NTSTATUS v29; // [rsp+6Ch] [rbp-4Dh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  __int128 *v31; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v32; // [rsp+88h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING v34; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v35[16]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v36; // [rsp+C0h] [rbp+7h] BYREF

  DestinationString = 0;
  *(_QWORD *)&Destination.Length = 0;
  *(_OWORD *)P = 0;
  v34 = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  Destination.Buffer = 0;
  KeyHandle = 0;
  v2 = BipConstructWorkItemKeyName(a1, P);
  if ( v2 >= 0 )
  {
    v2 = BipCreateKey(::KeyHandle, &KeyHandle, P);
    if ( v2 >= 0 )
    {
      RtlInitUnicodeString(&ValueName, L"ActivationType");
      v2 = BipWriteRegUlong(KeyHandle, &ValueName);
      if ( v2 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 624) )
        {
          Destination.Length = 0;
          Destination.MaximumLength = 90 * *(_WORD *)(a1 + 624) + 2;
          Heap = (WCHAR *)RtlAllocateHeap(BipHeap, 0, Destination.MaximumLength);
          Destination.Buffer = Heap;
          if ( !Heap )
          {
            v2 = -1073741801;
            v3 = 40;
            goto LABEL_53;
          }
          memset_0(Heap, 0, Destination.MaximumLength);
          v5 = 0;
          if ( *(_DWORD *)(a1 + 624) )
          {
            while ( 1 )
            {
              RtlFreeUnicodeString(&DestinationString);
              v6 = 32LL * v5;
              v2 = RtlStringFromGUID((const GUID *const)(*(_QWORD *)(v6 + a1 + 632) + 32LL), &DestinationString);
              if ( v2 < 0 )
                break;
              RtlAppendUnicodeStringToString(&Destination, &DestinationString);
              Destination.Length += 2;
              v7 = L"False";
              if ( *(_BYTE *)(v6 + a1 + 656) )
                v7 = L"True";
              RtlAppendUnicodeToString(&Destination, v7);
              ++v5;
              Length = Destination.Length + 2;
              Destination.Length += 2;
              if ( v5 >= *(_DWORD *)(a1 + 624) )
                goto LABEL_18;
            }
            v3 = 50;
            goto LABEL_53;
          }
          Length = Destination.Length;
LABEL_18:
          Destination.Buffer[(unsigned __int64)Length >> 1] = 0;
          RtlInitUnicodeString(&ValueName, L"Conditions");
          v2 = BipWriteRegMultiSz(KeyHandle, &ValueName);
          if ( v2 < 0 )
          {
            v3 = 60;
            goto LABEL_53;
          }
        }
        RtlInitUnicodeString(&ValueName, L"Flags");
        v2 = BipWriteRegUlong(KeyHandle, &ValueName);
        if ( v2 >= 0 )
        {
          if ( *(_QWORD *)(a1 + 392)
            && (RtlInitUnicodeString(&ValueName, L"Name"), v2 = BipWriteRegUnicodeString(KeyHandle, &ValueName), v2 < 0) )
          {
            v3 = 80;
          }
          else
          {
            RtlInitUnicodeString(&ValueName, L"TriggerEvent");
            v2 = BipWriteRegGuid(KeyHandle, &ValueName, (GUID *)(*(_QWORD *)(a1 + 72) + 32LL));
            if ( v2 >= 0 )
            {
              v11 = *(_DWORD *)(a1 + 400);
              if ( v11 )
              {
                v12 = (unsigned int)(v11 - 1);
                if ( (_DWORD)v12 )
                {
                  if ( (_DWORD)v12 == 1 )
                  {
                    RtlInitUnicodeString(&ValueName, L"TaskEntryPointId");
                    v2 = BipWriteRegGuid(KeyHandle, &ValueName, (GUID *)(a1 + 416));
                    if ( v2 < 0 )
                    {
                      v3 = 120;
                      goto LABEL_53;
                    }
                  }
                  else
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v9, v10);
                  }
                }
                else
                {
                  RtlInitUnicodeString(&ValueName, L"StateName");
                  v2 = BipWriteRegBinary(KeyHandle, &ValueName, (PVOID)(a1 + 416), 8u);
                  if ( v2 < 0 )
                  {
                    v3 = 110;
                    goto LABEL_53;
                  }
                }
              }
              else
              {
                RtlInitUnicodeString(&ValueName, L"TaskEntryPoint");
                BipWorkItemGetEntryPoint(a1);
                v2 = BipWriteRegUnicodeString(KeyHandle, &ValueName);
                if ( v2 < 0 )
                {
                  v3 = 100;
                  goto LABEL_53;
                }
              }
              if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(a1 + 400))
                && (v13 = *(_QWORD *)(a1 + 88)) != 0
                && (RtlInitUnicodeString(&v34, (PCWSTR)(v13 + 60)),
                    RtlInitUnicodeString(&ValueName, L"PackageRelativeAppName"),
                    v2 = BipWriteRegUnicodeString(KeyHandle, &ValueName),
                    v2 < 0) )
              {
                v3 = 130;
              }
              else if ( !(unsigned __int8)BipUtilActTypeIsResourceTimerSupported(*(unsigned int *)(a1 + 400))
                     || (unsigned __int8)BipUtilActTypeIsHostedInWinMainApp(v14)
                     || (RtlInitUnicodeString(&ValueName, L"PsmActivationType"),
                         BipGetActivationType(a1),
                         v2 = BipWriteRegUlong(KeyHandle, &ValueName),
                         v2 >= 0) )
              {
                if ( !(unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(a1 + 400))
                  || (RtlInitUnicodeString(&ValueName, L"PackageFlags"),
                      v2 = BipWriteRegUlong(KeyHandle, &ValueName),
                      v2 >= 0) )
                {
                  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(a1 + 400)) )
                  {
                    RtlInitUnicodeString(&ValueName, L"ExtendedRegistrationData");
                    v15 = *(void **)(a1 + 616);
                    if ( v15 && (v16 = *(_DWORD *)(a1 + 608)) != 0 )
                    {
                      v2 = BipWriteRegBinary(KeyHandle, &ValueName, v15, v16);
                      if ( v2 < 0 )
                      {
                        v3 = 160;
                        goto LABEL_53;
                      }
                    }
                    else
                    {
                      NtDeleteValueKey(KeyHandle, &ValueName);
                    }
                  }
                  v2 = 0;
                  goto LABEL_58;
                }
                v3 = 150;
              }
              else
              {
                v3 = 140;
              }
            }
            else
            {
              v3 = 90;
            }
          }
        }
        else
        {
          v3 = 70;
        }
      }
      else
      {
        v3 = 30;
      }
    }
    else
    {
      v3 = 20;
    }
  }
  else
  {
    v3 = 10;
  }
LABEL_53:
  if ( (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v3) )
  {
    v28 = v17;
    v29 = v2;
    WorkItemId = (__int128 *)BipWorkItemGetWorkItemId(v35, a1);
    v32 = 0;
    v19 = *WorkItemId;
    v31 = &v36;
    v36 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v20,
      (__int64)&dword_1800B51FC,
      v21,
      v22,
      &v32,
      (__int64 *)&v31,
      (__int64)&v29,
      (__int64)&v28);
  }
LABEL_58:
  RtlFreeUnicodeString(&DestinationString);
  if ( Destination.Buffer )
    RtlFreeHeap(BipHeap, 0, Destination.Buffer);
  v23 = KeyHandle;
  if ( KeyHandle )
  {
    if ( v2 < 0 )
    {
      NtDeleteKey(KeyHandle);
      v23 = KeyHandle;
    }
    NtClose(v23);
  }
  if ( P[1] )
    RtlFreeHeap(BipHeap, 0, P[1]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180064214  push    rbp
0x180064216  push    rbx
0x180064217  push    rsi
0x180064218  push    rdi
0x180064219  push    r12
0x18006421b  push    r14
0x18006421d  lea     rbp, [rsp-2Fh]
0x180064222  sub     rsp, 0E8h
0x180064229  mov     rax, cs:__security_cookie
0x180064230  xor     rax, rsp
0x180064233  mov     [rbp+57h+var_40], rax
0x180064237  xorps   xmm0, xmm0
0x18006423a  mov     [rbp+57h+KeyHandle], 0
0x180064242  xorps   xmm1, xmm1
0x180064245  mov     rdi, rcx
0x180064248  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006424c  xor     edx, edx; SourceString
0x18006424e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180064252  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x180064256  movups  xmmword ptr [rbp+57h+P], xmm0
0x18006425a  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x18006425e  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180064262  call    cs:__imp_RtlInitUnicodeString
0x180064268  lea     rdx, [rbp+57h+P]
0x18006426c  mov     [rbp+57h+Destination.Buffer], 0
0x180064274  mov     rcx, rdi
0x180064277  mov     [rbp+57h+KeyHandle], 0
0x18006427f  call    BipConstructWorkItemKeyName
0x180064284  mov     ebx, eax
0x180064286  mov     r12d, 2
0x18006428c  test    eax, eax
0x18006428e  jns     short loc_18006429A
0x180064290  lea     r8d, [r12+8]
0x180064295  jmp     loc_18006471B
0x18006429a  mov     rcx, cs:KeyHandle
0x1800642a1  lea     r8, [rbp+57h+P]
0x1800642a5  lea     rdx, [rbp+57h+KeyHandle]
0x1800642a9  call    BipCreateKey
0x1800642ae  mov     ebx, eax
0x1800642b0  test    eax, eax
0x1800642b2  jns     short loc_1800642BF
0x1800642b4  mov     r8d, 14h
0x1800642ba  jmp     loc_18006471B
0x1800642bf  lea     rdx, aActivationtype; "ActivationType"
0x1800642c6  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800642ca  call    cs:__imp_RtlInitUnicodeString
0x1800642d0  mov     r8d, [rdi+190h]
0x1800642d7  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800642db  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800642df  call    BipWriteRegUlong
0x1800642e4  mov     ebx, eax
0x1800642e6  test    eax, eax
0x1800642e8  jns     short loc_1800642F5
0x1800642ea  mov     r8d, 1Eh
0x1800642f0  jmp     loc_18006471B
0x1800642f5  cmp     dword ptr [rdi+270h], 0
0x1800642fc  jz      loc_18006442F
0x180064302  xor     eax, eax
0x180064304  xor     edx, edx; Flags
0x180064306  mov     [rbp+57h+Destination.Length], ax
0x18006430a  movzx   eax, word ptr [rdi+270h]
0x180064311  imul    ecx, eax, 5Ah ; 'Z'
0x180064314  add     cx, r12w
0x180064318  movzx   r8d, cx; Size
0x18006431c  mov     rcx, cs:BipHeap; HeapHandle
0x180064323  mov     [rbp+57h+Destination.MaximumLength], r8w
0x180064328  call    cs:__imp_RtlAllocateHeap
0x18006432e  mov     [rbp+57h+Destination.Buffer], rax
0x180064332  test    rax, rax
0x180064335  jnz     short loc_180064345
0x180064337  mov     ebx, 0C0000017h
0x18006433c  lea     r8d, [rax+28h]
0x180064340  jmp     loc_18006471B
0x180064345  movzx   r8d, [rbp+57h+Destination.MaximumLength]; Size
0x18006434a  xor     edx, edx; Val
0x18006434c  mov     rcx, rax; void *
0x18006434f  call    memset_0
0x180064354  xor     esi, esi
0x180064356  cmp     [rdi+270h], esi
0x18006435c  jbe     loc_1800643E8
0x180064362  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180064366  call    cs:__imp_RtlFreeUnicodeString
0x18006436c  mov     r14d, esi
0x18006436f  lea     rdx, [rbp+57h+DestinationString]; GuidString
0x180064373  shl     r14, 5
0x180064377  mov     rcx, [r14+rdi+278h]
0x18006437f  add     rcx, 20h ; ' '; Guid
0x180064383  call    cs:__imp_RtlStringFromGUID
0x180064389  mov     ebx, eax
0x18006438b  test    eax, eax
0x18006438d  js      short loc_1800643DD
0x18006438f  lea     rdx, [rbp+57h+DestinationString]; Source
0x180064393  lea     rcx, [rbp+57h+Destination]; Destination
0x180064397  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006439d  add     [rbp+57h+Destination.Length], r12w
0x1800643a2  lea     rcx, [rbp+57h+Destination]; Destination
0x1800643a6  cmp     byte ptr [r14+rdi+290h], 0
0x1800643af  lea     rdx, aFalse; "False"
0x1800643b6  jz      short loc_1800643BF
0x1800643b8  lea     rdx, aTrue; "True"
0x1800643bf  call    cs:__imp_RtlAppendUnicodeToString
0x1800643c5  movzx   eax, [rbp+57h+Destination.Length]
0x1800643c9  inc     esi
0x1800643cb  add     ax, r12w
0x1800643cf  mov     [rbp+57h+Destination.Length], ax
0x1800643d3  cmp     esi, [rdi+270h]
0x1800643d9  jb      short loc_180064362
0x1800643db  jmp     short loc_1800643EC
0x1800643dd  mov     r8d, 32h ; '2'
0x1800643e3  jmp     loc_18006471B
0x1800643e8  movzx   eax, [rbp+57h+Destination.Length]
0x1800643ec  movzx   edx, ax
0x1800643ef  xor     ecx, ecx
0x1800643f1  mov     rax, [rbp+57h+Destination.Buffer]
0x1800643f5  shr     rdx, 1
0x1800643f8  mov     [rax+rdx*2], cx
0x1800643fc  lea     rdx, aConditions; "Conditions"
0x180064403  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180064407  call    cs:__imp_RtlInitUnicodeString
0x18006440d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180064411  lea     r8, [rbp+57h+Destination]
0x180064415  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064419  call    BipWriteRegMultiSz
0x18006441e  mov     ebx, eax
0x180064420  test    eax, eax
0x180064422  jns     short loc_18006442F
0x180064424  mov     r8d, 3Ch ; '<'
0x18006442a  jmp     loc_18006471B
0x18006442f  lea     rdx, aFlags; "Flags"
0x180064436  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18006443a  call    cs:__imp_RtlInitUnicodeString
0x180064440  mov     r8d, [rdi+18h]
0x180064444  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064448  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006444c  and     r8d, 9FFFFFFh
0x180064453  call    BipWriteRegUlong
0x180064458  mov     ebx, eax
0x18006445a  test    eax, eax
0x18006445c  jns     short loc_180064469
0x18006445e  mov     r8d, 46h ; 'F'
0x180064464  jmp     loc_18006471B
0x180064469  lea     rbx, [rdi+180h]
0x180064470  cmp     qword ptr [rbx+8], 0
0x180064475  jz      short loc_1800644A9
0x180064477  lea     rdx, aName; "Name"
0x18006447e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180064482  call    cs:__imp_RtlInitUnicodeString
0x180064488  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006448c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064490  mov     r8, rbx
0x180064493  call    BipWriteRegUnicodeString
0x180064498  mov     ebx, eax
0x18006449a  test    eax, eax
0x18006449c  jns     short loc_1800644A9
0x18006449e  mov     r8d, 50h ; 'P'
0x1800644a4  jmp     loc_18006471B
0x1800644a9  lea     rdx, aTriggerevent; "TriggerEvent"
0x1800644b0  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800644b4  call    cs:__imp_RtlInitUnicodeString
0x1800644ba  mov     r8, [rdi+48h]
0x1800644be  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800644c2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800644c6  add     r8, 20h ; ' '; Guid
0x1800644ca  call    BipWriteRegGuid
0x1800644cf  mov     ebx, eax
0x1800644d1  test    eax, eax
0x1800644d3  jns     short loc_1800644E0
0x1800644d5  mov     r8d, 5Ah ; 'Z'
0x1800644db  jmp     loc_18006471B
0x1800644e0  mov     ecx, [rdi+190h]
0x1800644e6  test    ecx, ecx
0x1800644e8  jz      loc_1800645E0
0x1800644ee  sub     ecx, 1
0x1800644f1  jz      loc_1800645A0
0x1800644f7  cmp     ecx, 1
0x1800644fa  jz      short loc_180064566
0x1800644fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064501  mov     ecx, [rdi+190h]
0x180064507  call    BipUtilActTypeIsDebugSupported
0x18006450c  test    al, al
0x18006450e  jz      loc_18006461E
0x180064514  mov     rdx, [rdi+58h]
0x180064518  test    rdx, rdx
0x18006451b  jz      loc_18006461E
0x180064521  add     rdx, 3Ch ; '<'; SourceString
0x180064525  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180064529  call    cs:__imp_RtlInitUnicodeString
0x18006452f  lea     rdx, aPackagerelativ_0; "PackageRelativeAppName"
0x180064536  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18006453a  call    cs:__imp_RtlInitUnicodeString
0x180064540  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180064544  lea     r8, [rbp+57h+var_70]
0x180064548  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18006454c  call    BipWriteRegUnicodeString
0x180064551  mov     ebx, eax
0x180064553  test    eax, eax
0x180064555  jns     loc_18006461E
0x18006455b  mov     r8d, 82h
0x180064561  jmp     loc_18006471B
0x180064566  lea     rdx, aTaskentrypoint; "TaskEntryPointId"
0x18006456d  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180064571  call    cs:__imp_RtlInitUnicodeString
0x180064577  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006457b  lea     r8, [rdi+1A0h]; Guid
0x180064582  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064586  call    BipWriteRegGuid
0x18006458b  mov     ebx, eax
0x18006458d  test    eax, eax
0x18006458f  jns     loc_180064501
0x180064595  mov     r8d, 78h ; 'x'
0x18006459b  jmp     loc_18006471B
0x1800645a0  lea     rdx, aStatename; "StateName"
0x1800645a7  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800645ab  call    cs:__imp_RtlInitUnicodeString
0x1800645b1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800645b5  lea     r8, [rdi+1A0h]; Data
0x1800645bc  mov     r9d, 8; DataSize
0x1800645c2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800645c6  call    BipWriteRegBinary
0x1800645cb  mov     ebx, eax
0x1800645cd  test    eax, eax
0x1800645cf  jns     loc_180064501
0x1800645d5  mov     r8d, 6Eh ; 'n'
0x1800645db  jmp     loc_18006471B
0x1800645e0  lea     rdx, aTaskentrypoint_0; "TaskEntryPoint"
0x1800645e7  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800645eb  call    cs:__imp_RtlInitUnicodeString
0x1800645f1  mov     rcx, rdi
0x1800645f4  call    BipWorkItemGetEntryPoint
0x1800645f9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800645fd  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064601  mov     r8, rax
0x180064604  call    BipWriteRegUnicodeString
0x180064609  mov     ebx, eax
0x18006460b  test    eax, eax
0x18006460d  jns     loc_180064501
0x180064613  mov     r8d, 64h ; 'd'
0x180064619  jmp     loc_18006471B
0x18006461e  mov     edx, [rdi+190h]
0x180064624  mov     ecx, edx
0x180064626  call    BipUtilActTypeIsResourceTimerSupported
0x18006462b  test    al, al
0x18006462d  jz      short loc_180064674
0x18006462f  mov     ecx, edx
0x180064631  call    BipUtilActTypeIsHostedInWinMainApp
0x180064636  test    al, al
0x180064638  jnz     short loc_180064674
0x18006463a  lea     rdx, aPsmactivationt; "PsmActivationType"
0x180064641  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180064645  call    cs:__imp_RtlInitUnicodeString
0x18006464b  mov     rcx, rdi
0x18006464e  call    BipGetActivationType
0x180064653  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180064657  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18006465b  mov     r8d, eax
0x18006465e  call    BipWriteRegUlong
0x180064663  mov     ebx, eax
0x180064665  test    eax, eax
0x180064667  jns     short loc_180064674
0x180064669  mov     r8d, 8Ch
0x18006466f  jmp     loc_18006471B
0x180064674  mov     ecx, [rdi+190h]
0x18006467a  call    BipUtilActTypeIsDebugSupported
0x18006467f  test    al, al
0x180064681  jz      short loc_1800646BA
0x180064683  lea     rdx, aPackageflags; "PackageFlags"
0x18006468a  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18006468e  call    cs:__imp_RtlInitUnicodeString
0x180064694  mov     r8, [rdi+50h]
0x180064698  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18006469c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800646a0  mov     r8d, [r8+238h]
0x1800646a7  call    BipWriteRegUlong
0x1800646ac  mov     ebx, eax
0x1800646ae  test    eax, eax
0x1800646b0  jns     short loc_1800646BA
0x1800646b2  mov     r8d, 96h
0x1800646b8  jmp     short loc_18006471B
0x1800646ba  mov     ecx, [rdi+190h]
0x1800646c0  call    BipUtilActTypeIsDebugSupported
0x1800646c5  test    al, al
0x1800646c7  jz      loc_1800647AA
0x1800646cd  lea     rdx, aExtendedregist; "ExtendedRegistrationData"
0x1800646d4  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800646d8  call    cs:__imp_RtlInitUnicodeString
0x1800646de  mov     r8, [rdi+268h]; Data
0x1800646e5  test    r8, r8
0x1800646e8  jz      loc_18006479C
0x1800646ee  mov     r9d, [rdi+260h]; DataSize
0x1800646f5  test    r9d, r9d
0x1800646f8  jz      loc_18006479C
0x1800646fe  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180064702  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180064706  call    BipWriteRegBinary
0x18006470b  mov     ebx, eax
0x18006470d  test    eax, eax
0x18006470f  jns     loc_1800647AA
0x180064715  mov     r8d, 0A0h
0x18006471b  mov     eax, cs:dword_1800C3098
0x180064721  cmp     eax, r12d
  ... truncated ...
```

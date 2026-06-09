# USBSTOR_AsyncNotifyInterruptPipeCompletion

- ea: `0x1400116a0`
- end: `0x14001180c`
- name: `USBSTOR_AsyncNotifyInterruptPipeCompletion`
- size: `364`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140010664`
- `0x1400116a0`
- `0x140012318`
- `0x1400123b4`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400117b9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400117b9`
- `ntoskrnl!RtlCompareMemory` at `0x14001176e`
- `ntoskrnl!RtlCompareMemory` at `0x14001176e`

## pseudocode

```c
__int64 __fastcall USBSTOR_AsyncNotifyInterruptPipeCompletion(PDEVICE_OBJECT DeviceObject, PIRP Irp, _QWORD *Context)
{
  __int64 v6; // rbx
  _QWORD *v7; // rdi
  NTSTATUS Status; // eax
  bool v9; // cf
  int Source2; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1128877633, DeviceObject, Irp, Irp->IoStatus.Status);
  if ( DeviceObject )
    Context = &DeviceObject->Type;
  v6 = Context[8];
  if ( *(_DWORD *)v6 == 558842960 )
  {
    v7 = *(_QWORD **)(v6 + 16);
    v6 = v7[8];
  }
  else if ( *(_DWORD *)v6 == 558842950 )
  {
    v7 = Context;
  }
  else
  {
    v7 = 0;
    v6 = 0;
  }
  *(_DWORD *)(v6 + 128) &= ~0x80u;
  Status = Irp->IoStatus.Status;
  if ( Status != -1073741810 && Status != -1073741536 )
  {
    v9 = *(_DWORD *)(v6 + 564) < 4u;
    Source2 = 1229083477;
    if ( !v9 && RtlCompareMemory(*(const void **)(v6 + 568), &Source2, 4u) == 4 )
    {
      USBSTOR_QueueMediaChangeNotify(Context, (PVOID)v6);
      USBSTOR_QueueAsyncNotification(Context, (PVOID)v6);
    }
  }
  USBSTOR_LogEntry(1667853921, v7, Irp, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v6 + 1832), Irp, 0x20u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400116a0  mov     [rsp+arg_8], rbx
0x1400116a5  mov     [rsp+arg_10], rbp
0x1400116aa  push    rsi
0x1400116ab  push    rdi
0x1400116ac  push    r14
0x1400116ae  sub     rsp, 20h
0x1400116b2  mov     rsi, r8
0x1400116b5  mov     rbp, rdx
0x1400116b8  mov     rbx, rcx
0x1400116bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116c2  lea     r14, WPP_GLOBAL_Control
0x1400116c9  cmp     rcx, r14
0x1400116cc  jz      short loc_1400116F0
0x1400116ce  mov     eax, [rcx+2Ch]
0x1400116d1  test    al, 1
0x1400116d3  jz      short loc_1400116F0
0x1400116d5  cmp     byte ptr [rcx+29h], 5
0x1400116d9  jb      short loc_1400116F0
0x1400116db  mov     rcx, [rcx+18h]
0x1400116df  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400116e6  mov     edx, 5Ch ; '\'
0x1400116eb  call    WPP_SF_
0x1400116f0  movsxd  r9, dword ptr [rbp+30h]
0x1400116f4  mov     r8, rbp
0x1400116f7  mov     rdx, rbx
0x1400116fa  mov     ecx, 43494E41h
0x1400116ff  call    USBSTOR_LogEntry
0x140011704  test    rbx, rbx
0x140011707  cmovnz  rsi, rbx
0x14001170b  mov     rbx, [rsi+40h]
0x14001170f  mov     eax, [rbx]
0x140011711  cmp     eax, 214F4450h
0x140011716  jnz     short loc_140011722
0x140011718  mov     rdi, [rbx+10h]
0x14001171c  mov     rbx, [rdi+40h]
0x140011720  jmp     short loc_140011732
0x140011722  cmp     eax, 214F4446h
0x140011727  jnz     short loc_14001172E
0x140011729  mov     rdi, rsi
0x14001172c  jmp     short loc_140011732
0x14001172e  xor     edi, edi
0x140011730  xor     ebx, ebx
0x140011732  btr     dword ptr [rbx+80h], 7
0x14001173a  mov     eax, [rbp+30h]
0x14001173d  cmp     eax, 0C000000Eh
0x140011742  jz      short loc_140011796
0x140011744  cmp     eax, 0C0000120h
0x140011749  jz      short loc_140011796
0x14001174b  cmp     dword ptr [rbx+234h], 4
0x140011752  mov     [rsp+38h+Source2], 49425355h
0x14001175a  jb      short loc_140011796
0x14001175c  mov     rcx, [rbx+238h]; Source1
0x140011763  lea     rdx, [rsp+38h+Source2]; Source2
0x140011768  mov     r8d, 4; Length
0x14001176e  call    cs:__imp_RtlCompareMemory
0x140011775  nop     dword ptr [rax+rax+00h]
0x14001177a  cmp     rax, 4
0x14001177e  jnz     short loc_140011796
0x140011780  mov     rdx, rbx; Context
0x140011783  mov     rcx, rsi; Object
0x140011786  call    USBSTOR_QueueMediaChangeNotify
0x14001178b  mov     rdx, rbx; Context
0x14001178e  mov     rcx, rsi; Object
0x140011791  call    USBSTOR_QueueAsyncNotification
0x140011796  xor     r9d, r9d
0x140011799  mov     r8, rbp
0x14001179c  mov     rdx, rdi
0x14001179f  mov     ecx, 63696E61h
0x1400117a4  call    USBSTOR_LogEntry
0x1400117a9  lea     rcx, [rbx+728h]; RemoveLock
0x1400117b0  mov     r8d, 20h ; ' '; RemlockSize
0x1400117b6  mov     rdx, rbp; Tag
0x1400117b9  call    cs:__imp_IoReleaseRemoveLockEx
0x1400117c0  nop     dword ptr [rax+rax+00h]
0x1400117c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117cc  cmp     rcx, r14
0x1400117cf  jz      short loc_1400117F3
0x1400117d1  mov     eax, [rcx+2Ch]
0x1400117d4  test    al, 1
0x1400117d6  jz      short loc_1400117F3
0x1400117d8  cmp     byte ptr [rcx+29h], 5
0x1400117dc  jb      short loc_1400117F3
0x1400117de  mov     rcx, [rcx+18h]
0x1400117e2  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400117e9  mov     edx, 5Dh ; ']'
0x1400117ee  call    WPP_SF_
0x1400117f3  mov     rbx, [rsp+38h+arg_8]
0x1400117f8  mov     eax, 0C0000016h
0x1400117fd  mov     rbp, [rsp+38h+arg_10]
0x140011802  add     rsp, 20h
0x140011806  pop     r14
0x140011808  pop     rdi
0x140011809  pop     rsi
0x14001180a  retn
```

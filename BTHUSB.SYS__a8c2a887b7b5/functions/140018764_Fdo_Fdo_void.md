# Fdo::~Fdo(void)

- ea: `0x140018764`
- end: `0x140018906`
- name: `??1Fdo@@AEAA@XZ`
- size: `418`
- prototype: `void __fastcall(Fdo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001c50`

## callees

- `0x14000187c`
- `0x140001ca8`
- `0x14000bcc8`
- `0x14000de00`
- `0x140018764`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14001880a`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14001880a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400187ef`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400187ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018868`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018881`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018868`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018881`

## pseudocode

```c
void __fastcall Fdo::~Fdo(PVOID *this)
{
  unsigned int RecorderLog; // eax
  _QWORD *v3; // rcx
  __int64 v4; // r10
  int v5; // edx
  char *v6; // rcx
  _QWORD *v7; // rdi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  struct RECORDER_LOG__ *v13; // rcx

  RecorderLog = (unsigned int)Fdo::GetRecorderLog((Fdo *)this);
  WPP_RECORDER_AND_TRACE_SF_q(
    *(_QWORD *)(v4 + 24),
    v5,
    *v3,
    RecorderLog,
    4,
    1,
    11,
    (__int64)WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids,
    *v3);
  v6 = (char *)this[3];
  if ( v6 )
  {
    IoAcquireRemoveLockEx(
      (PIO_REMOVE_LOCK)(v6 + 48),
      this[2],
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\fdo.cpp",
      0x2Bu,
      0x20u);
    IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)((char *)this[3] + 48), this[2], 0x20u);
    v7 = this[3];
    v8 = (void *)v7[4];
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      v7[4] = 0;
      *((_DWORD *)v7 + 6) = 0;
    }
    v9 = (void *)v7[12];
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0);
      v7[12] = 0;
    }
    v10 = (void *)v7[13];
    if ( v10 )
    {
      ExFreePoolWithTag(v10, 0);
      v7[13] = 0;
    }
    ExFreePoolWithTag(v7, 0);
    *(_QWORD *)this[2] = 0;
    this[2] = 0;
  }
  v11 = this[5];
  if ( v11 )
    ((void (__fastcall *)(_LIST_ENTRY *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[104].Flink)(
      WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
      *v11);
  v12 = this[4];
  if ( v12 )
    ((void (__fastcall *)(_LIST_ENTRY *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[104].Flink)(
      WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
      *v12);
  v13 = (struct RECORDER_LOG__ *)this[1];
  if ( v13 )
    WppRecorderLogCloseFunction(v13);
}

```

## disassembly

```asm
0x140018764  mov     [rsp+arg_0], rbx
0x140018769  push    rdi
0x14001876a  sub     rsp, 50h
0x14001876e  mov     rbx, rcx
0x140018771  mov     r10, cs:WPP_GLOBAL_Control
0x140018778  mov     eax, [r10+2Ch]
0x14001877c  test    al, 1
0x14001877e  jz      short loc_14001878B
0x140018780  cmp     byte ptr [r10+29h], 4
0x140018785  jb      short loc_14001878B
0x140018787  mov     dl, 1
0x140018789  jmp     short loc_14001878D
0x14001878b  xor     dl, dl
0x14001878d  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140018792  mov     r8, [rcx]
0x140018795  mov     r9, rax
0x140018798  mov     [rsp+58h+var_18], r8
0x14001879d  lea     rcx, WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids
0x1400187a4  mov     [rsp+58h+var_20], rcx
0x1400187a9  mov     rcx, [r10+18h]
0x1400187ad  mov     [rsp+58h+var_28], 0Bh
0x1400187b4  mov     [rsp+58h+var_30], 1
0x1400187bc  mov     byte ptr [rsp+58h+RemlockSize], 4
0x1400187c1  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400187c6  mov     rcx, [rbx+18h]
0x1400187ca  test    rcx, rcx
0x1400187cd  jz      loc_1400188A0
0x1400187d3  mov     rdx, [rbx+10h]; Tag
0x1400187d7  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400187de  mov     edi, 20h ; ' '
0x1400187e3  add     rcx, 30h ; '0'; RemoveLock
0x1400187e7  mov     [rsp+58h+RemlockSize], edi; RemlockSize
0x1400187eb  lea     r9d, [rdi+0Bh]; Line
0x1400187ef  call    cs:__imp_IoAcquireRemoveLockEx
0x1400187f6  nop     dword ptr [rax+rax+00h]
0x1400187fb  mov     rcx, [rbx+18h]
0x1400187ff  mov     r8d, edi; RemlockSize
0x140018802  mov     rdx, [rbx+10h]; Tag
0x140018806  add     rcx, 30h ; '0'; RemoveLock
0x14001880a  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140018811  nop     dword ptr [rax+rax+00h]
0x140018816  mov     rdi, [rbx+18h]
0x14001881a  mov     rcx, [rdi+20h]; P
0x14001881e  test    rcx, rcx
0x140018821  jz      short loc_14001883E
0x140018823  xor     edx, edx; Tag
0x140018825  call    cs:__imp_ExFreePoolWithTag
0x14001882c  nop     dword ptr [rax+rax+00h]
0x140018831  xor     eax, eax
0x140018833  mov     qword ptr [rdi+20h], 0
0x14001883b  mov     [rdi+18h], eax
0x14001883e  mov     rcx, [rdi+60h]; P
0x140018842  test    rcx, rcx
0x140018845  jz      short loc_14001885D
0x140018847  xor     edx, edx; Tag
0x140018849  call    cs:__imp_ExFreePoolWithTag
0x140018850  nop     dword ptr [rax+rax+00h]
0x140018855  mov     qword ptr [rdi+60h], 0
0x14001885d  mov     rcx, [rdi+68h]; P
0x140018861  test    rcx, rcx
0x140018864  jz      short loc_14001887C
0x140018866  xor     edx, edx; Tag
0x140018868  call    cs:__imp_ExFreePoolWithTag
0x14001886f  nop     dword ptr [rax+rax+00h]
0x140018874  mov     qword ptr [rdi+68h], 0
0x14001887c  xor     edx, edx; Tag
0x14001887e  mov     rcx, rdi; P
0x140018881  call    cs:__imp_ExFreePoolWithTag
0x140018888  nop     dword ptr [rax+rax+00h]
0x14001888d  mov     rax, [rbx+10h]
0x140018891  mov     qword ptr [rax], 0
0x140018898  mov     qword ptr [rbx+10h], 0
0x1400188a0  mov     rdx, [rbx+28h]
0x1400188a4  test    rdx, rdx
0x1400188a7  jz      short loc_1400188C6
0x1400188a9  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x1400188b0  mov     rdx, [rdx]
0x1400188b3  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400188ba  mov     rax, [rax+680h]
0x1400188c1  call    _guard_dispatch_icall
0x1400188c6  mov     rdx, [rbx+20h]
0x1400188ca  test    rdx, rdx
0x1400188cd  jz      short loc_1400188EC
0x1400188cf  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x1400188d6  mov     rdx, [rdx]
0x1400188d9  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400188e0  mov     rax, [rax+680h]
0x1400188e7  call    _guard_dispatch_icall
0x1400188ec  mov     rcx, [rbx+8]; struct RECORDER_LOG__ *
0x1400188f0  test    rcx, rcx
0x1400188f3  jz      short loc_1400188FA
0x1400188f5  call    ?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z; WppRecorderLogCloseFunction(RECORDER_LOG__ *)
0x1400188fa  mov     rbx, [rsp+58h+arg_0]
0x1400188ff  add     rsp, 50h
0x140018903  pop     rdi
0x140018904  retn
```

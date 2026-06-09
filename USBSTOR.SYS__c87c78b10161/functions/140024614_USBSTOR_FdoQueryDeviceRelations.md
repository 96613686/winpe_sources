# USBSTOR_FdoQueryDeviceRelations

- ea: `0x140024614`
- end: `0x140024868`
- name: `USBSTOR_FdoQueryDeviceRelations`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010e74`
- `0x140024614`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140024761`
- `ntoskrnl!ExAllocatePool2` at `0x1400247ab`
- `ntoskrnl!ExAllocatePool2` at `0x140024761`
- `ntoskrnl!ExAllocatePool2` at `0x1400247ab`
- `ntoskrnl!ObfReferenceObject` at `0x1400247ed`
- `ntoskrnl!ObfReferenceObject` at `0x1400247ed`
- `ntoskrnl!IofCallDriver` at `0x1400246b3`
- `ntoskrnl!IofCallDriver` at `0x1400246b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024790`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024790`
- `ntoskrnl!IofCompleteRequest` at `0x140024857`
- `ntoskrnl!IofCompleteRequest` at `0x140024857`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoQueryDeviceRelations(__int64 a1, IRP *a2)
{
  __int64 v3; // r13
  __int64 Length; // rbx
  NTSTATUS v6; // ebx
  _QWORD **v8; // r14
  _QWORD *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned int *Information; // rbp
  unsigned int v13; // r12d
  __int64 v14; // rsi
  _DWORD *Pool2; // r15
  unsigned int v16; // ebp
  _QWORD *i; // rbx

  v3 = *(_QWORD *)(a1 + 64);
  Length = (int)a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1380208966, a1, a2, Length);
  if ( (_DWORD)Length )
    goto LABEL_6;
  v8 = (_QWORD **)(v3 + 32);
  v9 = *(_QWORD **)(v3 + 32);
  if ( v9 == (_QWORD *)(v3 + 32) )
    goto LABEL_6;
  v10 = 0;
  do
  {
    v9 = (_QWORD *)*v9;
    v11 = v10++;
  }
  while ( v9 != v8 );
  Information = (unsigned int *)a2->IoStatus.Information;
  if ( Information )
  {
    v13 = *Information;
    v14 = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 8LL * (v10 + *Information - 1) + 16, 1396788565);
    if ( Pool2 && v13 )
    {
      do
      {
        *(_QWORD *)&Pool2[2 * v14 + 2] = *(_QWORD *)&Information[2 * v14 + 2];
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < v13 );
    }
    ExFreePoolWithTag(Information, 0);
  }
  else
  {
    v13 = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 8 * v11 + 16, 1396788565);
    v14 = 0;
  }
  if ( Pool2 )
  {
    v16 = v10 + v13;
    *Pool2 = v10 + v13;
    for ( i = *v8; i != v8 && (unsigned int)v14 < v16; i = (_QWORD *)*i )
    {
      *(_QWORD *)&Pool2[2 * v14 + 2] = *(i - 2);
      v14 = (unsigned int)(v14 + 1);
      ObfReferenceObject((PVOID)*(i - 2));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_354602438fa331ce245c005e63ec86c9_Traceguids, *(i - 2));
      }
    }
    v6 = 0;
  }
  else
  {
    v6 = -1073741670;
    Pool2 = 0;
  }
  a2->IoStatus.Status = v6;
  a2->IoStatus.Information = (ULONG_PTR)Pool2;
  if ( v6 >= 0 )
  {
LABEL_6:
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v6 = IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 24), a2);
  }
  else
  {
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1919185254, v6, 0, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140024614  push    rbx
0x140024616  push    rbp
0x140024617  push    rsi
0x140024618  push    rdi
0x140024619  push    r12
0x14002461b  push    r13
0x14002461d  push    r14
0x14002461f  push    r15
0x140024621  sub     rsp, 28h
0x140024625  mov     rax, [rdx+0B8h]
0x14002462c  mov     rdi, rdx
0x14002462f  mov     r13, [rcx+40h]
0x140024633  mov     rsi, rcx
0x140024636  movsxd  rbx, dword ptr [rax+8]
0x14002463a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024641  lea     rax, WPP_GLOBAL_Control
0x140024648  cmp     rcx, rax
0x14002464b  jz      short loc_140024672
0x14002464d  mov     eax, [rcx+2Ch]
0x140024650  test    al, 2
0x140024652  jz      short loc_140024672
0x140024654  cmp     byte ptr [rcx+29h], 4
0x140024658  jb      short loc_140024672
0x14002465a  mov     rcx, [rcx+18h]
0x14002465e  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024665  mov     edx, 68h ; 'h'
0x14002466a  mov     r9d, ebx
0x14002466d  call    WPP_SF_d
0x140024672  mov     r9, rbx
0x140024675  mov     r8, rdi
0x140024678  mov     rdx, rsi
0x14002467b  mov     ecx, 52445146h
0x140024680  call    USBSTOR_LogEntry
0x140024685  test    ebx, ebx
0x140024687  jz      loc_14002471A
0x14002468d  sub     ebx, 1
0x140024690  jz      short loc_14002469A
0x140024692  sub     ebx, 1
0x140024695  jz      short loc_14002469A
0x140024697  sub     ebx, 1
0x14002469a  lea     r12, WPP_GLOBAL_Control
0x1400246a1  inc     byte ptr [rdi+43h]
0x1400246a4  mov     rdx, rdi; Irp
0x1400246a7  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400246af  mov     rcx, [r13+18h]; DeviceObject
0x1400246b3  call    cs:__imp_IofCallDriver
0x1400246ba  nop     dword ptr [rax+rax+00h]
0x1400246bf  mov     ebx, eax
0x1400246c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400246c8  cmp     rcx, r12
0x1400246cb  jz      short loc_1400246F3
0x1400246cd  mov     edx, [rcx+2Ch]
0x1400246d0  test    dl, 2
0x1400246d3  jz      short loc_1400246F3
0x1400246d5  cmp     byte ptr [rcx+29h], 4
0x1400246d9  jb      short loc_1400246F3
0x1400246db  mov     rcx, [rcx+18h]
0x1400246df  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400246e6  mov     edx, 6Ah ; 'j'
0x1400246eb  mov     r9d, ebx
0x1400246ee  call    WPP_SF_d
0x1400246f3  movsxd  rdx, ebx
0x1400246f6  xor     r9d, r9d
0x1400246f9  xor     r8d, r8d
0x1400246fc  mov     ecx, 72647166h
0x140024701  call    USBSTOR_LogEntry
0x140024706  mov     eax, ebx
0x140024708  add     rsp, 28h
0x14002470c  pop     r15
0x14002470e  pop     r14
0x140024710  pop     r13
0x140024712  pop     r12
0x140024714  pop     rdi
0x140024715  pop     rsi
0x140024716  pop     rbp
0x140024717  pop     rbx
0x140024718  retn
0x14002471a  lea     r14, [r13+20h]
0x14002471e  mov     rax, [r14]
0x140024721  cmp     rax, r14
0x140024724  jz      loc_14002469A
0x14002472a  xor     ebx, ebx
0x14002472c  mov     rax, [rax]
0x14002472f  mov     ecx, ebx
0x140024731  inc     ebx
0x140024733  cmp     rax, r14
0x140024736  jnz     short loc_14002472C
0x140024738  mov     rbp, [rdi+38h]
0x14002473c  mov     r8d, 53414D55h
0x140024742  test    rbp, rbp
0x140024745  jz      short loc_14002479E
0x140024747  mov     r12d, [rbp+0]
0x14002474b  mov     ecx, 100h
0x140024750  xor     esi, esi
0x140024752  lea     eax, [r12-1]
0x140024757  add     eax, ebx
0x140024759  lea     rdx, ds:10h[rax*8]
0x140024761  call    cs:__imp_ExAllocatePool2
0x140024768  nop     dword ptr [rax+rax+00h]
0x14002476d  mov     r15, rax
0x140024770  test    rax, rax
0x140024773  jz      short loc_14002478B
0x140024775  test    r12d, r12d
0x140024778  jz      short loc_14002478B
0x14002477a  mov     rax, [rbp+rsi*8+8]
0x14002477f  mov     [r15+rsi*8+8], rax
0x140024784  inc     esi
0x140024786  cmp     esi, r12d
0x140024789  jb      short loc_14002477A
0x14002478b  xor     edx, edx; Tag
0x14002478d  mov     rcx, rbp; P
0x140024790  call    cs:__imp_ExFreePoolWithTag
0x140024797  nop     dword ptr [rax+rax+00h]
0x14002479c  jmp     short loc_1400247BF
0x14002479e  lea     rdx, ds:10h[rcx*8]
0x1400247a6  mov     ecx, 100h
0x1400247ab  call    cs:__imp_ExAllocatePool2
0x1400247b2  nop     dword ptr [rax+rax+00h]
0x1400247b7  xor     r12d, r12d
0x1400247ba  mov     r15, rax
0x1400247bd  xor     esi, esi
0x1400247bf  test    r15, r15
0x1400247c2  jz      short loc_140024834
0x1400247c4  lea     ebp, [rbx+r12]
0x1400247c8  mov     [r15], ebp
0x1400247cb  lea     r12, WPP_GLOBAL_Control
0x1400247d2  mov     rbx, [r14]
0x1400247d5  cmp     rbx, r14
0x1400247d8  jz      short loc_140024830
0x1400247da  cmp     esi, ebp
0x1400247dc  jnb     short loc_140024830
0x1400247de  mov     rax, [rbx-10h]
0x1400247e2  mov     [r15+rsi*8+8], rax
0x1400247e7  inc     esi
0x1400247e9  mov     rcx, [rbx-10h]; Object
0x1400247ed  call    cs:__imp_ObfReferenceObject
0x1400247f4  nop     dword ptr [rax+rax+00h]
0x1400247f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140024800  cmp     rcx, r12
0x140024803  jz      short loc_14002482B
0x140024805  mov     eax, [rcx+2Ch]
0x140024808  test    al, 2
0x14002480a  jz      short loc_14002482B
0x14002480c  cmp     byte ptr [rcx+29h], 4
0x140024810  jb      short loc_14002482B
0x140024812  mov     r9, [rbx-10h]
0x140024816  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002481d  mov     rcx, [rcx+18h]
0x140024821  mov     edx, 69h ; 'i'
0x140024826  call    WPP_SF_q
0x14002482b  mov     rbx, [rbx]
0x14002482e  jmp     short loc_1400247D5
0x140024830  xor     ebx, ebx
0x140024832  jmp     short loc_140024843
0x140024834  mov     ebx, 0C000009Ah
0x140024839  lea     r12, WPP_GLOBAL_Control
0x140024840  xor     r15d, r15d
0x140024843  mov     [rdi+30h], ebx
0x140024846  mov     [rdi+38h], r15
0x14002484a  test    ebx, ebx
0x14002484c  jns     loc_1400246A1
0x140024852  xor     edx, edx; PriorityBoost
0x140024854  mov     rcx, rdi; Irp
0x140024857  call    cs:__imp_IofCompleteRequest
0x14002485e  nop     dword ptr [rax+rax+00h]
0x140024863  jmp     loc_1400246C1
```

# FltpNamePurgeWorker

- ea: `0x180077430`
- end: `0x1800776af`
- name: `FltpNamePurgeWorker`
- size: `639`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180024800`
- `0x180024c40`
- `0x1800614b0`
- `0x180077430`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180077486`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180077486`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007756c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180077600`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18007756c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180077600`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007754e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800775e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007754e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800775e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800775d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800775d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077634`
- `ntoskrnl!ExReleaseFastResource` at `0x1800775c4`
- `ntoskrnl!ExReleaseFastResource` at `0x180077628`
- `ntoskrnl!ExReleaseFastResource` at `0x1800775c4`
- `ntoskrnl!ExReleaseFastResource` at `0x180077628`
- `ntoskrnl!ExSetTimer` at `0x18007766b`
- `ntoskrnl!ExSetTimer` at `0x18007766b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1800774fa`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1800774fa`
- `ntoskrnl!ExCancelTimer` at `0x180077538`
- `ntoskrnl!ExCancelTimer` at `0x180077538`
- `ntoskrnl!PsTerminateSystemThread` at `0x18007767e`
- `ntoskrnl!PsTerminateSystemThread` at `0x18007767e`

## string_xrefs

- `0x1800775a4`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c
void __fastcall FltpNamePurgeWorker(PVOID StartContext)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  NTSTATUS v3; // eax
  int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rbp
  __int64 v7; // r8
  _QWORD *v8; // r14
  _QWORD *v9; // rbx
  _QWORD *v10; // r15
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r8
  _BYTE v14[80]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v15[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 Object; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v17; // [rsp+B0h] [rbp-58h]

  v17 = 0;
  v1 = 0;
  v2 = 0;
  Object = 0;
  memset(v14, 0, 0x48u);
  ExInitializeFastOwnerEntry(v14);
  *(_QWORD *)&Object = &Event;
  *((_QWORD *)&Object + 1) = &stru_180040418;
  v17 = qword_180040430;
  while ( 1 )
  {
    while ( 1 )
    {
      v3 = KeWaitForMultipleObjects(3u, (PVOID *)&Object, WaitAny, Executive, 0, 0, 0, 0);
      if ( v3 )
        break;
      if ( ++v1 >= v2 + 32 )
      {
        ExCancelTimer(qword_180040430, 0);
        goto LABEL_9;
      }
      v15[0] = 0;
      v15[1] = -1;
      ExSetTimer(qword_180040430, -1200000000, 0, v15);
    }
    v4 = v3 - 1;
    if ( !v4 )
      break;
    if ( v4 == 1 && v1 > v2 )
    {
LABEL_9:
      v5 = qword_18003ED88;
      v2 = v1;
      KeEnterCriticalRegion();
      v6 = v5 + 192;
      LOBYTE(v7) = 1;
      ExAcquireFastResourceShared(v5 + 192, v14, v7);
      v8 = (_QWORD *)(v5 + 296);
      v9 = *(_QWORD **)(v5 + 296);
      while ( v9 != v8 )
      {
        v10 = v9 - 2;
        v11 = FltObjectReference(v9 - 2);
        if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7984, 3223060491LL) >= 0 )
        {
          ExReleaseFastResource(v6, v14);
          KeLeaveCriticalRegion();
          LOBYTE(v12) = 1;
          FltpPurgeVolumeNameCache(v9 - 2, 0, v12);
          KeEnterCriticalRegion();
          LOBYTE(v13) = 1;
          ExAcquireFastResourceShared(v6, v14, v13);
          v9 = (_QWORD *)*v9;
          FltObjectDereference(v10);
        }
        else
        {
          v9 = (_QWORD *)*v9;
        }
      }
      ExReleaseFastResource(v6, v14);
      KeLeaveCriticalRegion();
    }
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x180077430  mov     r11, rsp
0x180077433  push    rbx
0x180077434  push    rbp
0x180077435  push    rsi
0x180077436  push    rdi
0x180077437  push    r12
0x180077439  push    r13
0x18007743b  push    r14
0x18007743d  push    r15
0x18007743f  sub     rsp, 0C8h
0x180077446  mov     rax, cs:__security_cookie
0x18007744d  xor     rax, rsp
0x180077450  mov     [rsp+108h+var_50], rax
0x180077458  xor     r12d, r12d
0x18007745b  lea     rcx, [rsp+108h+var_C8]; void *
0x180077460  xorps   xmm0, xmm0
0x180077463  xor     eax, eax
0x180077465  xor     edx, edx; Val
0x180077467  mov     [r11-58h], rax
0x18007746b  mov     r8d, 48h ; 'H'; Size
0x180077471  mov     edi, r12d
0x180077474  mov     esi, r12d
0x180077477  movups  xmmword ptr [r11-68h], xmm0
0x18007747c  call    memset
0x180077481  lea     rcx, [rsp+108h+var_C8]
0x180077486  call    cs:__imp_ExInitializeFastOwnerEntry
0x18007748d  nop     dword ptr [rax+rax+00h]
0x180077492  lea     rax, Event
0x180077499  mov     r13d, 1F30h
0x18007749f  mov     [rsp+108h+Object], rax
0x1800774a7  lea     rax, stru_180040418
0x1800774ae  mov     [rsp+108h+var_60], rax
0x1800774b6  mov     rax, cs:qword_180040430
0x1800774bd  mov     [rsp+108h+var_58], rax
0x1800774c5  nop     word ptr [rax+rax+00000000h]
0x1800774d0  mov     [rsp+108h+WaitBlockArray], r12; WaitBlockArray
0x1800774d5  lea     rdx, [rsp+108h+Object]; Object
0x1800774dd  mov     [rsp+108h+Timeout], r12; Timeout
0x1800774e2  xor     r9d, r9d; WaitReason
0x1800774e5  mov     [rsp+108h+Alertable], r12b; Alertable
0x1800774ea  mov     r8d, 1; WaitType
0x1800774f0  mov     ecx, 3; Count
0x1800774f5  mov     [rsp+108h+WaitMode], r12b; WaitMode
0x1800774fa  call    cs:__imp_KeWaitForMultipleObjects
0x180077501  nop     dword ptr [rax+rax+00h]
0x180077506  test    eax, eax
0x180077508  jz      short loc_18007751F
0x18007750a  sub     eax, 1
0x18007750d  jz      loc_18007767C
0x180077513  cmp     eax, 1
0x180077516  jnz     short loc_1800774D0
0x180077518  cmp     rdi, rsi
0x18007751b  jle     short loc_1800774D0
0x18007751d  jmp     short loc_180077544
0x18007751f  mov     rcx, cs:qword_180040430
0x180077526  lea     rax, [rsi+20h]
0x18007752a  inc     rdi
0x18007752d  cmp     rdi, rax
0x180077530  jl      loc_180077645
0x180077536  xor     edx, edx
0x180077538  call    cs:__imp_ExCancelTimer
0x18007753f  nop     dword ptr [rax+rax+00h]
0x180077544  mov     rbx, cs:qword_18003ED88
0x18007754b  mov     rsi, rdi
0x18007754e  call    cs:__imp_KeEnterCriticalRegion
0x180077555  nop     dword ptr [rax+rax+00h]
0x18007755a  lea     rbp, [rbx+0C0h]
0x180077561  mov     r8b, 1
0x180077564  mov     rcx, rbp
0x180077567  lea     rdx, [rsp+108h+var_C8]
0x18007756c  call    cs:__imp_ExAcquireFastResourceShared
0x180077573  nop     dword ptr [rax+rax+00h]
0x180077578  lea     r14, [rbx+128h]
0x18007757f  mov     rbx, [r14]
0x180077582  cmp     rbx, r14
0x180077585  jz      loc_180077620
0x18007758b  lea     r15, [rbx-10h]
0x18007758f  mov     rcx, r15; FltObject
0x180077592  call    FltObjectReference
0x180077597  mov     ecx, eax
0x180077599  mov     qword ptr [rsp+108h+WaitMode], r12
0x18007759e  mov     r9d, 0C01C000Bh
0x1800775a4  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x1800775ab  mov     r8d, r13d
0x1800775ae  call    FltpDbgStatus
0x1800775b3  test    eax, eax
0x1800775b5  jns     short loc_1800775BC
0x1800775b7  mov     rbx, [rbx]
0x1800775ba  jmp     short loc_180077617
0x1800775bc  lea     rdx, [rsp+108h+var_C8]
0x1800775c1  mov     rcx, rbp
0x1800775c4  call    cs:__imp_ExReleaseFastResource
0x1800775cb  nop     dword ptr [rax+rax+00h]
0x1800775d0  call    cs:__imp_KeLeaveCriticalRegion
0x1800775d7  nop     dword ptr [rax+rax+00h]
0x1800775dc  mov     r8b, 1
0x1800775df  xor     edx, edx
0x1800775e1  mov     rcx, r15
0x1800775e4  call    FltpPurgeVolumeNameCache
0x1800775e9  call    cs:__imp_KeEnterCriticalRegion
0x1800775f0  nop     dword ptr [rax+rax+00h]
0x1800775f5  mov     r8b, 1
0x1800775f8  lea     rdx, [rsp+108h+var_C8]
0x1800775fd  mov     rcx, rbp
0x180077600  call    cs:__imp_ExAcquireFastResourceShared
0x180077607  nop     dword ptr [rax+rax+00h]
0x18007760c  mov     rbx, [rbx]
0x18007760f  mov     rcx, r15; FltObject
0x180077612  call    FltObjectDereference
0x180077617  cmp     rbx, r14
0x18007761a  jnz     loc_18007758B
0x180077620  lea     rdx, [rsp+108h+var_C8]
0x180077625  mov     rcx, rbp
0x180077628  call    cs:__imp_ExReleaseFastResource
0x18007762f  nop     dword ptr [rax+rax+00h]
0x180077634  call    cs:__imp_KeLeaveCriticalRegion
0x18007763b  nop     dword ptr [rax+rax+00h]
0x180077640  jmp     loc_1800774D0
0x180077645  lea     r9, [rsp+108h+var_78]
0x18007764d  mov     [rsp+108h+var_78], r12
0x180077655  xor     r8d, r8d
0x180077658  mov     [rsp+108h+var_70], 0FFFFFFFFFFFFFFFFh
0x180077664  mov     rdx, 0FFFFFFFFB8797400h
0x18007766b  call    cs:__imp_ExSetTimer
0x180077672  nop     dword ptr [rax+rax+00h]
0x180077677  jmp     loc_1800774D0
0x18007767c  xor     ecx, ecx; ExitStatus
0x18007767e  call    cs:__imp_PsTerminateSystemThread
0x180077685  nop     dword ptr [rax+rax+00h]
0x18007768a  mov     rcx, [rsp+108h+var_50]
0x180077692  xor     rcx, rsp; StackCookie
0x180077695  call    __security_check_cookie
0x18007769a  add     rsp, 0C8h
0x1800776a1  pop     r15
0x1800776a3  pop     r14
0x1800776a5  pop     r13
0x1800776a7  pop     r12
0x1800776a9  pop     rdi
0x1800776aa  pop     rsi
0x1800776ab  pop     rbp
0x1800776ac  pop     rbx
0x1800776ad  retn
```

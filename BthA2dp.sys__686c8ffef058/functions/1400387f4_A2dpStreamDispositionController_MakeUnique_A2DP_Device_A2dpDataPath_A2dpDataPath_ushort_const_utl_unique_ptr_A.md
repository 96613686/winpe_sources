# A2dpStreamDispositionController::MakeUnique(A2DP_Device *,A2dpDataPath &,A2dpDataPath &,ushort const *,utl::unique_ptr<A2dpStreamDispositionController,utl::default_delete<A2dpStreamDispositionController>> &)

- ea: `0x1400387f4`
- end: `0x140038975`
- name: `?MakeUnique@A2dpStreamDispositionController@@SAJPEAVA2DP_Device@@AEAVA2dpDataPath@@1PEBGAEAV?$unique_ptr@VA2dpStreamDispositionController@@U?$default_delete@VA2dpStreamDispositionController@@@utl@@@utl@@@Z`
- size: `385`
- prototype: `__int64 __usercall@<rax>(struct A2DP_Device *@<rcx>, struct A2dpDataPath *@<rdx>, struct A2dpDataPath *@<r8>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140079ecc`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x14002090c`
- `0x14002b9b4`
- `0x1400387f4`
- `0x140082e04`
- `0x140083090`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140038819`
- `ntoskrnl!ExAllocatePool2` at `0x140038819`

## pseudocode

```c
__int64 __fastcall A2dpStreamDispositionController::MakeUnique(
        struct A2DP_Device *a1,
        struct A2dpDataPath *a2,
        struct A2dpDataPath *a3,
        const unsigned __int16 *a4,
        PVOID *a5)
{
  A2dpStreamDispositionController *Pool2; // rax
  PVOID v10; // rdx
  int v11; // edx
  int v12; // r8d
  int v14; // edx
  int v15; // ebx
  int v16; // r8d
  _QWORD v17[7]; // [rsp+50h] [rbp-38h] BYREF

  Pool2 = (A2dpStreamDispositionController *)ExAllocatePool2(64, 224, 1684882288);
  if ( Pool2 )
    Pool2 = A2dpStreamDispositionController::A2dpStreamDispositionController(Pool2, a1, a2, a3);
  v17[0] = 0;
  v10 = *a5;
  *a5 = Pool2;
  if ( v10 )
    utl::default_delete<A2dpStreamDispositionController>::operator()();
  utl::unique_ptr<A2dpStreamDispositionController,utl::default_delete<A2dpStreamDispositionController>>::~unique_ptr<A2dpStreamDispositionController,utl::default_delete<A2dpStreamDispositionController>>(v17);
  if ( *a5 )
  {
    v15 = A2dpStreamDispositionController::Initialize(*a5, a4);
    if ( v15 < 0 )
    {
      LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v14,
          v16,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          11,
          (__int64)WPP_ad4b63f66cf5370f3cc05f32705bbd55_Traceguids,
          v15);
      }
    }
    return (unsigned int)v15;
  }
  else
  {
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        10,
        (__int64)WPP_ad4b63f66cf5370f3cc05f32705bbd55_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400387f4  push    rbx
0x1400387f6  push    rbp
0x1400387f7  push    rsi
0x1400387f8  push    rdi
0x1400387f9  sub     rsp, 68h
0x1400387fd  mov     rbx, r8
0x140038800  mov     rsi, rdx
0x140038803  mov     rbp, rcx
0x140038806  mov     edx, 0E0h
0x14003880b  mov     ecx, 40h ; '@'
0x140038810  mov     r8d, 646D4370h
0x140038816  mov     rdi, r9
0x140038819  call    cs:__imp_ExAllocatePool2
0x140038820  nop     dword ptr [rax+rax+00h]
0x140038825  test    rax, rax
0x140038828  jz      short loc_14003883B
0x14003882a  mov     r9, rbx; struct A2dpDataPath *
0x14003882d  mov     r8, rsi; struct A2dpDataPath *
0x140038830  mov     rdx, rbp; struct A2DP_Device *
0x140038833  mov     rcx, rax; this
0x140038836  call    ??0A2dpStreamDispositionController@@QEAA@PEAVA2DP_Device@@AEAVA2dpDataPath@@1@Z; A2dpStreamDispositionController::A2dpStreamDispositionController(A2DP_Device *,A2dpDataPath &,A2dpDataPath &)
0x14003883b  mov     rbx, [rsp+88h+arg_20]
0x140038843  mov     [rsp+88h+var_38], 0
0x14003884c  mov     rdx, [rbx]
0x14003884f  mov     [rbx], rax
0x140038852  test    rdx, rdx
0x140038855  jz      short loc_14003885C
0x140038857  call    ??R?$default_delete@VA2dpStreamDispositionController@@@utl@@QEBAXPEAVA2dpStreamDispositionController@@@Z; utl::default_delete<A2dpStreamDispositionController>::operator()(A2dpStreamDispositionController *)
0x14003885c  lea     rcx, [rsp+88h+var_38]
0x140038861  call    ??1?$unique_ptr@VA2dpStreamDispositionController@@U?$default_delete@VA2dpStreamDispositionController@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<A2dpStreamDispositionController,utl::default_delete<A2dpStreamDispositionController>>::~unique_ptr<A2dpStreamDispositionController,utl::default_delete<A2dpStreamDispositionController>>(void)
0x140038866  mov     rcx, [rbx]; DeferredContext
0x140038869  test    rcx, rcx
0x14003886c  jnz     short loc_1400388E6
0x14003886e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038875  lea     rax, WPP_GLOBAL_Control
0x14003887c  cmp     rcx, rax
0x14003887f  jz      short loc_140038892
0x140038881  mov     eax, [rcx+2Ch]
0x140038884  test    al, 10h
0x140038886  jz      short loc_140038892
0x140038888  cmp     byte ptr [rcx+29h], 2
0x14003888c  jb      short loc_140038892
0x14003888e  mov     dl, 1
0x140038890  jmp     short loc_140038894
0x140038892  xor     dl, dl
0x140038894  lea     rax, WPP_RECORDER_INITIALIZED
0x14003889b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400388a2  setnz   r8b
0x1400388a6  test    dl, dl
0x1400388a8  jnz     short loc_1400388AF
0x1400388aa  test    r8b, r8b
0x1400388ad  jz      short loc_1400388DC
0x1400388af  mov     r9, [rcx+40h]
0x1400388b3  lea     rax, WPP_ad4b63f66cf5370f3cc05f32705bbd55_Traceguids
0x1400388ba  mov     rcx, [rcx+18h]
0x1400388be  mov     [rsp+88h+var_50], rax
0x1400388c3  mov     [rsp+88h+var_58], 0Ah
0x1400388ca  mov     [rsp+88h+var_60], 5
0x1400388d2  mov     [rsp+88h+var_68], 2
0x1400388d7  call    WPP_RECORDER_AND_TRACE_SF_
0x1400388dc  mov     eax, 0C000009Ah
0x1400388e1  jmp     loc_14003896B
0x1400388e6  mov     rdx, rdi; unsigned __int16 *
0x1400388e9  call    ?Initialize@A2dpStreamDispositionController@@AEAAJPEBG@Z; A2dpStreamDispositionController::Initialize(ushort const *)
0x1400388ee  mov     ebx, eax
0x1400388f0  test    eax, eax
0x1400388f2  jns     short loc_140038969
0x1400388f4  mov     r10, cs:WPP_GLOBAL_Control
0x1400388fb  lea     rax, WPP_GLOBAL_Control
0x140038902  cmp     r10, rax
0x140038905  jz      short loc_14003891B
0x140038907  mov     ecx, [r10+2Ch]
0x14003890b  test    cl, 10h
0x14003890e  jz      short loc_14003891B
0x140038910  cmp     byte ptr [r10+29h], 2
0x140038915  jb      short loc_14003891B
0x140038917  mov     dl, 1
0x140038919  jmp     short loc_14003891D
0x14003891b  xor     dl, dl
0x14003891d  lea     rax, WPP_RECORDER_INITIALIZED
0x140038924  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003892b  setnz   r8b
0x14003892f  test    dl, dl
0x140038931  jnz     short loc_140038938
0x140038933  test    r8b, r8b
0x140038936  jz      short loc_140038969
0x140038938  mov     r9, [r10+40h]
0x14003893c  lea     rax, WPP_ad4b63f66cf5370f3cc05f32705bbd55_Traceguids
0x140038943  mov     rcx, [r10+18h]
0x140038947  mov     [rsp+88h+var_48], ebx
0x14003894b  mov     [rsp+88h+var_50], rax
0x140038950  mov     [rsp+88h+var_58], 0Bh
0x140038957  mov     [rsp+88h+var_60], 5
0x14003895f  mov     [rsp+88h+var_68], 2
0x140038964  call    WPP_RECORDER_AND_TRACE_SF_d
0x140038969  mov     eax, ebx
0x14003896b  add     rsp, 68h
0x14003896f  pop     rdi
0x140038970  pop     rsi
0x140038971  pop     rbp
0x140038972  pop     rbx
0x140038973  retn
```

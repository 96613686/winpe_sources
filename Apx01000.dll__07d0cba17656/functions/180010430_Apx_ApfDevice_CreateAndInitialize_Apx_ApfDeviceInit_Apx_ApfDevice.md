# Apx::ApfDevice::_CreateAndInitialize(Apx::ApfDeviceInit *,Apx::ApfDevice * *)

- ea: `0x180010430`
- end: `0x180010513`
- name: `?_CreateAndInitialize@ApfDevice@Apx@@SAJPEAVApfDeviceInit@2@PEAPEAV12@@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct Apx::ApfDeviceInit *, struct Apx::ApfDevice **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010570`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000e6b0`
- `0x18000fb6c`
- `0x180010430`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::_CreateAndInitialize(struct Apx::ApfDeviceInit *a1, struct Apx::ApfDevice **a2)
{
  Apx::ApfDevice *v4; // rax
  Apx::ApfDevice *v5; // rbx
  int v6; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfDevice *)operator new(0x810u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = (Apx::ApfDevice *)Apx::ApfDevice::ApfDevice(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    v6 = Apx::ApfDevice::Initialize(v5, a1);
    if ( v6 < 0 )
    {
      (**(void (__fastcall ***)(Apx::ApfDevice *, __int64))v5)(v5, 1);
    }
    else
    {
      *a2 = v5;
      v6 = 0;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010430  push    rbx
0x180010432  push    rbp
0x180010433  push    rsi
0x180010434  push    rdi
0x180010435  sub     rsp, 28h
0x180010439  mov     rsi, rdx
0x18001043c  mov     rdi, rcx
0x18001043f  lea     rbp, WPP_GLOBAL_Control
0x180010446  mov     rcx, cs:WPP_GLOBAL_Control
0x18001044d  cmp     rcx, rbp
0x180010450  jz      short loc_180010473
0x180010452  test    byte ptr [rcx+1Ch], 1
0x180010456  jz      short loc_180010473
0x180010458  cmp     byte ptr [rcx+19h], 5
0x18001045c  jb      short loc_180010473
0x18001045e  mov     edx, 0Ah
0x180010463  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18001046a  mov     rcx, [rcx+10h]
0x18001046e  call    WPP_SF_
0x180010473  mov     qword ptr [rsi], 0
0x18001047a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010481  mov     ecx, 810h; unsigned __int64
0x180010486  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001048b  mov     [rsp+48h+arg_8], rax
0x180010490  test    rax, rax
0x180010493  jz      short loc_1800104A2
0x180010495  mov     rcx, rax; this
0x180010498  call    ??0ApfDevice@Apx@@AEAA@XZ; Apx::ApfDevice::ApfDevice(void)
0x18001049d  mov     rbx, rax
0x1800104a0  jmp     short loc_1800104A4
0x1800104a2  xor     ebx, ebx
0x1800104a4  test    rbx, rbx
0x1800104a7  jnz     short loc_1800104B0
0x1800104a9  mov     edi, 8007000Eh
0x1800104ae  jmp     short loc_1800104DB
0x1800104b0  mov     rdx, rdi; struct Apx::ApfDeviceInit *
0x1800104b3  mov     rcx, rbx; this
0x1800104b6  call    ?Initialize@ApfDevice@Apx@@AEAAJPEAVApfDeviceInit@2@@Z; Apx::ApfDevice::Initialize(Apx::ApfDeviceInit *)
0x1800104bb  mov     edi, eax
0x1800104bd  test    eax, eax
0x1800104bf  js      short loc_1800104C8
0x1800104c1  mov     [rsi], rbx
0x1800104c4  xor     edi, edi
0x1800104c6  jmp     short loc_1800104DB
0x1800104c8  mov     rax, [rbx]
0x1800104cb  mov     edx, 1
0x1800104d0  mov     rcx, rbx
0x1800104d3  mov     rax, [rax]
0x1800104d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104e2  cmp     rcx, rbp
0x1800104e5  jz      short loc_180010508
0x1800104e7  test    byte ptr [rcx+1Ch], 1
0x1800104eb  jz      short loc_180010508
0x1800104ed  cmp     byte ptr [rcx+19h], 5
0x1800104f1  jb      short loc_180010508
0x1800104f3  mov     edx, 0Bh
0x1800104f8  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x1800104ff  mov     rcx, [rcx+10h]
0x180010503  call    WPP_SF_
0x180010508  mov     eax, edi
0x18001050a  add     rsp, 28h
0x18001050e  pop     rdi
0x18001050f  pop     rsi
0x180010510  pop     rbp
0x180010511  pop     rbx
0x180010512  retn
```

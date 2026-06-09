# Apx::ApfStream::AddIpcLink(Apx::ApfIpcLink *)

- ea: `0x180019afc`
- end: `0x180019c07`
- name: `?AddIpcLink@ApfStream@Apx@@QEAAXPEAVApfIpcLink@2@@Z`
- size: `267`
- prototype: `void __fastcall(Apx::ApfStream *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017ba4`

## callees

- `0x18000a12c`
- `0x18000d3c0`
- `0x180019afc`
- `0x18002a010`

## pseudocode

```c
void __fastcall Apx::ApfStream::AddIpcLink(Apx::ApfStream *this, unsigned __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  v4 = *((unsigned int *)this + 19);
  *((_DWORD *)this + 10) = 4;
  *((_DWORD *)this + v4 + 11) = 4;
  if ( ++*((_DWORD *)this + 19) >= 8u )
    *((_DWORD *)this + 19) = 0;
  imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~a2);
  *((_QWORD *)this + 4) = a2;
  v5 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)a2 + 48LL))(a2);
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 3) = v5;
  (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(Apx::ApfStream *, __int16, struct APF_MESSAGE *, unsigned int, void *, unsigned int, unsigned int *), Apx::ApfStream *))(*(_QWORD *)v6 + 16LL))(
    v6,
    Apx::ApfStream::_CommandHandler,
    this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
}

```

## disassembly

```asm
0x180019afc  mov     [rsp+arg_0], rbx
0x180019b01  mov     [rsp+arg_8], rsi
0x180019b06  push    rdi
0x180019b07  sub     rsp, 30h
0x180019b0b  mov     rdi, rdx
0x180019b0e  mov     rbx, rcx
0x180019b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b18  lea     rsi, WPP_GLOBAL_Control
0x180019b1f  cmp     rcx, rsi
0x180019b22  jz      short loc_180019B45
0x180019b24  test    byte ptr [rcx+1Ch], 1
0x180019b28  jz      short loc_180019B45
0x180019b2a  cmp     byte ptr [rcx+19h], 5
0x180019b2e  jb      short loc_180019B45
0x180019b30  mov     rcx, [rcx+10h]
0x180019b34  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x180019b3b  mov     edx, 14h
0x180019b40  call    WPP_SF_
0x180019b45  mov     eax, [rbx+4Ch]
0x180019b48  mov     ecx, 4
0x180019b4d  mov     [rbx+28h], ecx
0x180019b50  mov     [rbx+rax*4+2Ch], ecx
0x180019b54  inc     dword ptr [rbx+4Ch]
0x180019b57  cmp     dword ptr [rbx+4Ch], 8
0x180019b5b  jb      short loc_180019B64
0x180019b5d  mov     dword ptr [rbx+4Ch], 0
0x180019b64  lea     rax, aOnecoreuapDriv_5; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180019b6b  mov     rdx, rdi
0x180019b6e  not     rdx; Apx::ApfVerify *
0x180019b71  mov     [rsp+38h+var_18], rax
0x180019b76  xor     ecx, ecx; this
0x180019b78  mov     r9d, 0B9h
0x180019b7e  mov     r8d, 44787041h
0x180019b84  call    imp_ApxObjectReferenceActual
0x180019b89  mov     [rbx+20h], rdi
0x180019b8d  mov     rcx, rdi
0x180019b90  mov     rax, [rdi]
0x180019b93  mov     rax, [rax+30h]
0x180019b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b9c  mov     rcx, [rbx+20h]
0x180019ba0  lea     rdx, ?_CommandHandler@ApfStream@Apx@@KAJPEAXGPEAUAPF_MESSAGE@@K0KPEAK@Z; Apx::ApfStream::_CommandHandler(void *,ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)
0x180019ba7  mov     [rbx+18h], rax
0x180019bab  mov     r8, rbx
0x180019bae  mov     rax, [rcx]
0x180019bb1  mov     rax, [rax+10h]
0x180019bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bba  mov     rcx, [rbx+20h]
0x180019bbe  mov     rax, [rcx]
0x180019bc1  mov     rax, [rax+18h]
0x180019bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bd1  cmp     rcx, rsi
0x180019bd4  jz      short loc_180019BF7
0x180019bd6  test    byte ptr [rcx+1Ch], 1
0x180019bda  jz      short loc_180019BF7
0x180019bdc  cmp     byte ptr [rcx+19h], 5
0x180019be0  jb      short loc_180019BF7
0x180019be2  mov     rcx, [rcx+10h]
0x180019be6  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x180019bed  mov     edx, 15h
0x180019bf2  call    WPP_SF_
0x180019bf7  mov     rbx, [rsp+38h+arg_0]
0x180019bfc  mov     rsi, [rsp+38h+arg_8]
0x180019c01  add     rsp, 30h
0x180019c05  pop     rdi
0x180019c06  retn
```

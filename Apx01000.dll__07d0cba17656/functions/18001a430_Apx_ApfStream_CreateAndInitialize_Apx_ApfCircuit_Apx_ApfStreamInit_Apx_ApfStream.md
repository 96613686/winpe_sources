# Apx::ApfStream::_CreateAndInitialize(Apx::ApfCircuit *,Apx::ApfStreamInit *,Apx::ApfStream * *)

- ea: `0x18001a430`
- end: `0x18001a50d`
- name: `?_CreateAndInitialize@ApfStream@Apx@@SAJPEAVApfCircuit@2@PEAVApfStreamInit@2@PEAPEAV12@@Z`
- size: `221`
- prototype: `__int64 __fastcall(struct Apx::ApfCircuit *, struct Apx::ApfStreamInit *, struct Apx::ApfStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a8c0`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x180019894`
- `0x180019cd4`
- `0x18001a430`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfStream::_CreateAndInitialize(
        struct Apx::ApfCircuit *a1,
        struct Apx::ApfStreamInit *a2,
        struct Apx::ApfStream **a3)
{
  Apx::ApfStream *v6; // rax
  Apx::ApfStream *v7; // rax
  struct Apx::ApfStream *v8; // rdi
  int v9; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  v6 = (Apx::ApfStream *)operator new(0x118u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 && (v7 = (Apx::ApfStream *)Apx::ApfStream::ApfStream(v6, a1), (v8 = v7) != 0) )
  {
    v9 = Apx::ApfStream::Initialize(v7, a2);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfStream *, __int64))v8)(v8, 1);
    }
    else
    {
      *a3 = v8;
      v9 = 0;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a430  push    rbx
0x18001a432  push    rbp
0x18001a433  push    rsi
0x18001a434  push    rdi
0x18001a435  push    r14
0x18001a437  sub     rsp, 20h
0x18001a43b  mov     rsi, r8
0x18001a43e  mov     rbp, rdx
0x18001a441  mov     rbx, rcx
0x18001a444  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a44b  lea     r14, WPP_GLOBAL_Control
0x18001a452  cmp     rcx, r14
0x18001a455  jz      short loc_18001A478
0x18001a457  test    byte ptr [rcx+1Ch], 1
0x18001a45b  jz      short loc_18001A478
0x18001a45d  cmp     byte ptr [rcx+19h], 5
0x18001a461  jb      short loc_18001A478
0x18001a463  mov     rcx, [rcx+10h]
0x18001a467  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a46e  mov     edx, 0Ah
0x18001a473  call    WPP_SF_
0x18001a478  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a47f  mov     ecx, 118h; unsigned __int64
0x18001a484  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a489  test    rax, rax
0x18001a48c  jz      short loc_18001A4CE
0x18001a48e  mov     rdx, rbx; struct Apx::ApfCircuit *
0x18001a491  mov     rcx, rax; this
0x18001a494  call    ??0ApfStream@Apx@@IEAA@PEAVApfCircuit@1@@Z; Apx::ApfStream::ApfStream(Apx::ApfCircuit *)
0x18001a499  mov     rdi, rax
0x18001a49c  test    rax, rax
0x18001a49f  jz      short loc_18001A4CE
0x18001a4a1  mov     rdx, rbp; struct Apx::ApfStreamInit *
0x18001a4a4  mov     rcx, rax; this
0x18001a4a7  call    ?Initialize@ApfStream@Apx@@IEAAJPEAVApfStreamInit@2@@Z; Apx::ApfStream::Initialize(Apx::ApfStreamInit *)
0x18001a4ac  mov     ebx, eax
0x18001a4ae  test    eax, eax
0x18001a4b0  js      short loc_18001A4B9
0x18001a4b2  mov     [rsi], rdi
0x18001a4b5  xor     ebx, ebx
0x18001a4b7  jmp     short loc_18001A4D3
0x18001a4b9  mov     rax, [rdi]
0x18001a4bc  mov     edx, 1
0x18001a4c1  mov     rcx, rdi
0x18001a4c4  mov     rax, [rax]
0x18001a4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4cc  jmp     short loc_18001A4D3
0x18001a4ce  mov     ebx, 8007000Eh
0x18001a4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4da  cmp     rcx, r14
0x18001a4dd  jz      short loc_18001A500
0x18001a4df  test    byte ptr [rcx+1Ch], 1
0x18001a4e3  jz      short loc_18001A500
0x18001a4e5  cmp     byte ptr [rcx+19h], 5
0x18001a4e9  jb      short loc_18001A500
0x18001a4eb  mov     rcx, [rcx+10h]
0x18001a4ef  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a4f6  mov     edx, 0Bh
0x18001a4fb  call    WPP_SF_
0x18001a500  mov     eax, ebx
0x18001a502  add     rsp, 20h
0x18001a506  pop     r14
0x18001a508  pop     rdi
0x18001a509  pop     rsi
0x18001a50a  pop     rbp
0x18001a50b  pop     rbx
0x18001a50c  retn
```

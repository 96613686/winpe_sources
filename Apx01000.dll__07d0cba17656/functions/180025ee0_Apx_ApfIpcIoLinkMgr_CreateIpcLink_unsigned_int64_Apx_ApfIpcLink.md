# Apx::ApfIpcIoLinkMgr::CreateIpcLink(unsigned __int64,Apx::ApfIpcLink * *)

- ea: `0x180025ee0`
- end: `0x1800260a6`
- name: `?CreateIpcLink@ApfIpcIoLinkMgr@Apx@@UEAAJ_KPEAPEAVApfIpcLink@2@@Z`
- size: `454`
- prototype: `__int64 __fastcall(Apx::ApfIpcIoLinkMgr *this, __int64, struct Apx::ApfIpcLink **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18000d3c0`
- `0x180025ee0`
- `0x18002732c`
- `0x18002a010`

## string_xrefs

- `0x180026040`: `onecoreuap\drivers\wdm\audio\backpln\apx\class\ipclinks\apfipciolinkmgr.cpp`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLinkMgr::CreateIpcLink(
        Apx::ApfIpcIoLinkMgr *this,
        __int64 a2,
        struct Apx::ApfIpcLink **a3)
{
  struct Apx::ApfIpcLink *v6; // rsi
  Apx::ApfIpcIoLink *v7; // rax
  Apx::ApfIpcIoLink *v8; // rdi
  int v9; // ebx
  _QWORD *v10; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  *a3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  v6 = 0;
  v7 = (Apx::ApfIpcIoLink *)operator new(0x1B8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v8 = Apx::ApfIpcIoLink::ApfIpcIoLink(v7, this, a2);
  else
    v8 = 0;
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(Apx::ApfIpcIoLink *))(*(_QWORD *)v8 + 72LL))(v8);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(Apx::ApfIpcIoLink *, __int64))v8)(v8, 1);
    }
    else
    {
      v6 = v8;
      v9 = 0;
    }
    goto LABEL_20;
  }
  v9 = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
LABEL_20:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
  {
    WPP_SF_(v10[2], 12, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
    imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~(unsigned __int64)v6);
    *a3 = v6;
    v9 = 0;
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_(v10[2], 73, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025ee0  mov     [rsp+arg_0], rbx
0x180025ee5  mov     [rsp+arg_8], rbp
0x180025eea  push    rsi
0x180025eeb  push    rdi
0x180025eec  push    r14
0x180025eee  sub     rsp, 30h
0x180025ef2  mov     r14, r8
0x180025ef5  mov     rbx, rdx
0x180025ef8  mov     rdi, rcx
0x180025efb  lea     rbp, WPP_GLOBAL_Control
0x180025f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f09  cmp     rcx, rbp
0x180025f0c  jz      short loc_180025F2F
0x180025f0e  test    byte ptr [rcx+1Ch], 1
0x180025f12  jz      short loc_180025F2F
0x180025f14  cmp     byte ptr [rcx+19h], 5
0x180025f18  jb      short loc_180025F2F
0x180025f1a  mov     edx, 48h ; 'H'
0x180025f1f  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025f26  mov     rcx, [rcx+10h]
0x180025f2a  call    WPP_SF_
0x180025f2f  mov     qword ptr [r14], 0
0x180025f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f3d  cmp     rcx, rbp
0x180025f40  jz      short loc_180025F63
0x180025f42  test    byte ptr [rcx+1Ch], 1
0x180025f46  jz      short loc_180025F63
0x180025f48  cmp     byte ptr [rcx+19h], 5
0x180025f4c  jb      short loc_180025F63
0x180025f4e  mov     edx, 0Ah
0x180025f53  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180025f5a  mov     rcx, [rcx+10h]
0x180025f5e  call    WPP_SF_
0x180025f63  xor     esi, esi
0x180025f65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025f6c  mov     ecx, 1B8h; unsigned __int64
0x180025f71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025f76  mov     [rsp+48h+arg_10], rax
0x180025f7b  test    rax, rax
0x180025f7e  jz      short loc_180025F93
0x180025f80  mov     r8, rbx; unsigned __int64
0x180025f83  mov     rdx, rdi; struct Apx::ApfIpcIoLinkMgr *
0x180025f86  mov     rcx, rax; this
0x180025f89  call    ??0ApfIpcIoLink@Apx@@AEAA@PEAVApfIpcIoLinkMgr@1@_K@Z; Apx::ApfIpcIoLink::ApfIpcIoLink(Apx::ApfIpcIoLinkMgr *,unsigned __int64)
0x180025f8e  mov     rdi, rax
0x180025f91  jmp     short loc_180025F95
0x180025f93  xor     edi, edi
0x180025f95  test    rdi, rdi
0x180025f98  jnz     short loc_180025FD3
0x180025f9a  mov     ebx, 8007000Eh
0x180025f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fa6  cmp     rcx, rbp
0x180025fa9  jz      loc_180026091
0x180025faf  test    byte ptr [rcx+1Ch], 20h
0x180025fb3  jz      short loc_180026009
0x180025fb5  cmp     byte ptr [rcx+19h], 2
0x180025fb9  jb      short loc_180026009
0x180025fbb  lea     edx, [rdi+0Bh]
0x180025fbe  mov     r9d, ebx
0x180025fc1  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180025fc8  mov     rcx, [rcx+10h]
0x180025fcc  call    WPP_SF_d
0x180025fd1  jmp     short loc_180026002
0x180025fd3  mov     rax, [rdi]
0x180025fd6  mov     rcx, rdi
0x180025fd9  mov     rax, [rax+48h]
0x180025fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fe2  mov     ebx, eax
0x180025fe4  test    eax, eax
0x180025fe6  js      short loc_180025FEF
0x180025fe8  mov     rsi, rdi
0x180025feb  xor     ebx, ebx
0x180025fed  jmp     short loc_180026002
0x180025fef  mov     rax, [rdi]
0x180025ff2  mov     edx, 1
0x180025ff7  mov     rcx, rdi
0x180025ffa  mov     rax, [rax]
0x180025ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026002  mov     rcx, cs:WPP_GLOBAL_Control
0x180026009  cmp     rcx, rbp
0x18002600c  jz      short loc_180026036
0x18002600e  test    byte ptr [rcx+1Ch], 1
0x180026012  jz      short loc_180026036
0x180026014  cmp     byte ptr [rcx+19h], 5
0x180026018  jb      short loc_180026036
0x18002601a  mov     edx, 0Ch
0x18002601f  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180026026  mov     rcx, [rcx+10h]
0x18002602a  call    WPP_SF_
0x18002602f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026036  test    ebx, ebx
0x180026038  js      short loc_18002606B
0x18002603a  mov     rdx, rsi
0x18002603d  not     rdx; Apx::ApfVerify *
0x180026040  lea     rax, aOnecoreuapDriv_4; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180026047  mov     [rsp+48h+var_28], rax
0x18002604c  xor     ecx, ecx; this
0x18002604e  mov     r9d, 3EEh
0x180026054  mov     r8d, 44787041h
0x18002605a  call    imp_ApxObjectReferenceActual
0x18002605f  mov     [r14], rsi
0x180026062  xor     ebx, ebx
0x180026064  mov     rcx, cs:WPP_GLOBAL_Control
0x18002606b  cmp     rcx, rbp
0x18002606e  jz      short loc_180026091
0x180026070  test    byte ptr [rcx+1Ch], 1
0x180026074  jz      short loc_180026091
0x180026076  cmp     byte ptr [rcx+19h], 5
0x18002607a  jb      short loc_180026091
0x18002607c  mov     edx, 49h ; 'I'
0x180026081  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026088  mov     rcx, [rcx+10h]
0x18002608c  call    WPP_SF_
0x180026091  mov     eax, ebx
0x180026093  mov     rbx, [rsp+48h+arg_0]
0x180026098  mov     rbp, [rsp+48h+arg_8]
0x18002609d  add     rsp, 30h
0x1800260a1  pop     r14
0x1800260a3  pop     rdi
0x1800260a4  pop     rsi
0x1800260a5  retn
```

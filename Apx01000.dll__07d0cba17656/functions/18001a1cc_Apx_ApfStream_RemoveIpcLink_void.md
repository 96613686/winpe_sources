# Apx::ApfStream::RemoveIpcLink(void)

- ea: `0x18001a1cc`
- end: `0x18001a2b7`
- name: `?RemoveIpcLink@ApfStream@Apx@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(Apx::ApfStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180016db0`
- `0x1800181ac`

## callees

- `0x18000a12c`
- `0x18000d2f0`
- `0x18001a1cc`
- `0x18002a010`

## pseudocode

```c
void __fastcall Apx::ApfStream::RemoveIpcLink(Apx::ApfStream *this)
{
  __int64 v2; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4));
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4), 0, 0);
  imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~*((_QWORD *)this + 4));
  *((_QWORD *)this + 4) = 0;
  v2 = *((unsigned int *)this + 19);
  *((_DWORD *)this + 10) = 3;
  *((_DWORD *)this + v2 + 11) = 3;
  if ( ++*((_DWORD *)this + 19) >= 8u )
    *((_DWORD *)this + 19) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
}

```

## disassembly

```asm
0x18001a1cc  mov     [rsp+arg_0], rbx
0x18001a1d1  push    rdi
0x18001a1d2  sub     rsp, 30h
0x18001a1d6  mov     rbx, rcx
0x18001a1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1e0  lea     rdi, WPP_GLOBAL_Control
0x18001a1e7  cmp     rcx, rdi
0x18001a1ea  jz      short loc_18001A20D
0x18001a1ec  test    byte ptr [rcx+1Ch], 1
0x18001a1f0  jz      short loc_18001A20D
0x18001a1f2  cmp     byte ptr [rcx+19h], 5
0x18001a1f6  jb      short loc_18001A20D
0x18001a1f8  mov     rcx, [rcx+10h]
0x18001a1fc  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a203  mov     edx, 16h
0x18001a208  call    WPP_SF_
0x18001a20d  mov     rcx, [rbx+20h]
0x18001a211  mov     rax, [rcx]
0x18001a214  mov     rax, [rax+20h]
0x18001a218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a21d  mov     rcx, [rbx+20h]
0x18001a221  xor     r8d, r8d
0x18001a224  xor     edx, edx
0x18001a226  mov     rax, [rcx]
0x18001a229  mov     rax, [rax+10h]
0x18001a22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a232  mov     rdx, [rbx+20h]
0x18001a236  lea     rax, aOnecoreuapDriv_5; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18001a23d  not     rdx; Apx::ApfVerify *
0x18001a240  mov     [rsp+38h+var_18], rax
0x18001a245  xor     ecx, ecx; this
0x18001a247  mov     r9d, 0CEh
0x18001a24d  mov     r8d, 44787041h
0x18001a253  call    imp_ApxObjectDereferenceActual
0x18001a258  mov     qword ptr [rbx+20h], 0
0x18001a260  mov     ecx, 3
0x18001a265  mov     eax, [rbx+4Ch]
0x18001a268  mov     [rbx+28h], ecx
0x18001a26b  mov     [rbx+rax*4+2Ch], ecx
0x18001a26f  inc     dword ptr [rbx+4Ch]
0x18001a272  cmp     dword ptr [rbx+4Ch], 8
0x18001a276  jb      short loc_18001A27F
0x18001a278  mov     dword ptr [rbx+4Ch], 0
0x18001a27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a286  cmp     rcx, rdi
0x18001a289  jz      short loc_18001A2AC
0x18001a28b  test    byte ptr [rcx+1Ch], 1
0x18001a28f  jz      short loc_18001A2AC
0x18001a291  cmp     byte ptr [rcx+19h], 5
0x18001a295  jb      short loc_18001A2AC
0x18001a297  mov     rcx, [rcx+10h]
0x18001a29b  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a2a2  mov     edx, 17h
0x18001a2a7  call    WPP_SF_
0x18001a2ac  mov     rbx, [rsp+38h+arg_0]
0x18001a2b1  add     rsp, 30h
0x18001a2b5  pop     rdi
0x18001a2b6  retn
```

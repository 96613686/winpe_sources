# Apx::ApfCircuitFactory::RemoveCircuit(Apx::ApfCircuit *)

- ea: `0x180011ab8`
- end: `0x180011cc7`
- name: `?RemoveCircuit@ApfCircuitFactory@Apx@@QEAAJPEAVApfCircuit@2@@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int64 this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012340`

## callees

- `0x18000a12c`
- `0x18000d2f0`
- `0x180011ab8`
- `0x180011e6c`
- `0x180011f50`
- `0x1800177a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b09`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuitFactory::RemoveCircuit(unsigned __int64 this, unsigned __int64 a2)
{
  unsigned int v4; // esi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  _QWORD *v8; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rsi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 64));
  if ( *(_QWORD *)(a2 + 584) == a2 + 584 )
  {
    v4 = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 33;
LABEL_17:
      WPP_SF_qqd(v5[2], v6, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids, ~this, ~a2, -2147024809);
    }
  }
  else
  {
    v7 = *(_QWORD **)(this + 104);
    if ( v7 == (_QWORD *)(this + 104) )
    {
LABEL_13:
      v4 = -2147024809;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 34;
        goto LABEL_17;
      }
    }
    else
    {
      while ( 1 )
      {
        v8 = (_QWORD *)*v7;
        if ( v7 - 73 == (_QWORD *)a2 )
          break;
        v7 = (_QWORD *)*v7;
        if ( v8 == (_QWORD *)(this + 104) )
          goto LABEL_13;
      }
      if ( (_QWORD *)v8[1] != v7 || (v10 = (_QWORD *)v7[1], (_QWORD *)*v10 != v7) )
        __fastfail(3u);
      *v10 = v8;
      v8[1] = v10;
      v7[1] = v7;
      *v7 = v7;
      v11 = *(_QWORD *)(a2 + 32);
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qqqqi(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_88d8f9f30453351596b6a72932727db3_Traceguids,
            ~this,
            ~*(_QWORD *)(this + 136),
            ~a2,
            ~v11,
            *(_QWORD *)(v11 + 64));
        }
        Apx::ApfCircuit::RemoveIpcLink((Apx::ApfCircuit *)a2);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(this + 136) + 56LL))(*(_QWORD *)(this + 136), v11);
      }
      imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~a2);
      v4 = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 64));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x180011ab8  push    rbx
0x180011aba  push    rbp
0x180011abb  push    rsi
0x180011abc  push    rdi
0x180011abd  push    r14
0x180011abf  push    r15
0x180011ac1  sub     rsp, 48h
0x180011ac5  mov     rbx, rdx
0x180011ac8  mov     rdi, rcx
0x180011acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ad2  lea     r14, WPP_GLOBAL_Control
0x180011ad9  lea     r15, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011ae0  cmp     rcx, r14
0x180011ae3  jz      short loc_180011B02
0x180011ae5  test    byte ptr [rcx+1Ch], 1
0x180011ae9  jz      short loc_180011B02
0x180011aeb  cmp     byte ptr [rcx+19h], 5
0x180011aef  jb      short loc_180011B02
0x180011af1  mov     rcx, [rcx+10h]
0x180011af5  mov     edx, 20h ; ' '
0x180011afa  mov     r8, r15
0x180011afd  call    WPP_SF_
0x180011b02  lea     rbp, [rdi+40h]
0x180011b06  mov     rcx, rbp; lpCriticalSection
0x180011b09  call    cs:__imp_EnterCriticalSection
0x180011b0f  lea     rax, [rbx+248h]
0x180011b16  cmp     [rax], rax
0x180011b19  jnz     short loc_180011B41
0x180011b1b  mov     eax, 80070057h
0x180011b20  mov     esi, eax
0x180011b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b29  cmp     rcx, r14
0x180011b2c  jz      short loc_180011BAA
0x180011b2e  test    byte ptr [rcx+1Ch], 20h
0x180011b32  jz      short loc_180011BAA
0x180011b34  cmp     byte ptr [rcx+19h], 2
0x180011b38  jb      short loc_180011BAA
0x180011b3a  mov     edx, 21h ; '!'
0x180011b3f  jmp     short loc_180011B8C
0x180011b41  lea     r8, [rdi+68h]
0x180011b45  mov     rcx, [r8]
0x180011b48  cmp     rcx, r8
0x180011b4b  jz      short loc_180011B68
0x180011b4d  mov     rdx, [rcx]
0x180011b50  lea     rax, [rcx-248h]
0x180011b57  cmp     rax, rbx
0x180011b5a  jz      loc_180011BEB
0x180011b60  mov     rcx, rdx
0x180011b63  cmp     rdx, r8
0x180011b66  jnz     short loc_180011B4D
0x180011b68  mov     eax, 80070057h
0x180011b6d  mov     esi, eax
0x180011b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b76  cmp     rcx, r14
0x180011b79  jz      short loc_180011BAA
0x180011b7b  test    byte ptr [rcx+1Ch], 20h
0x180011b7f  jz      short loc_180011BAA
0x180011b81  cmp     byte ptr [rcx+19h], 2
0x180011b85  jb      short loc_180011BAA
0x180011b87  mov     edx, 22h ; '"'
0x180011b8c  mov     rcx, [rcx+10h]
0x180011b90  not     rdi
0x180011b93  mov     dword ptr [rsp+78h+var_50], eax
0x180011b97  not     rbx
0x180011b9a  mov     r9, rdi
0x180011b9d  mov     [rsp+78h+var_58], rbx
0x180011ba2  mov     r8, r15
0x180011ba5  call    WPP_SF_qqd
0x180011baa  mov     rcx, rbp; lpCriticalSection
0x180011bad  call    cs:__imp_LeaveCriticalSection
0x180011bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bba  cmp     rcx, r14
0x180011bbd  jz      short loc_180011BDC
0x180011bbf  test    byte ptr [rcx+1Ch], 1
0x180011bc3  jz      short loc_180011BDC
0x180011bc5  cmp     byte ptr [rcx+19h], 5
0x180011bc9  jb      short loc_180011BDC
0x180011bcb  mov     rcx, [rcx+10h]
0x180011bcf  mov     edx, 24h ; '$'
0x180011bd4  mov     r8, r15
0x180011bd7  call    WPP_SF_
0x180011bdc  mov     eax, esi
0x180011bde  add     rsp, 48h
0x180011be2  pop     r15
0x180011be4  pop     r14
0x180011be6  pop     rdi
0x180011be7  pop     rsi
0x180011be8  pop     rbp
0x180011be9  pop     rbx
0x180011bea  retn
0x180011beb  cmp     [rdx+8], rcx
0x180011bef  jnz     loc_180011CC0
0x180011bf5  mov     rax, [rcx+8]
0x180011bf9  cmp     [rax], rcx
0x180011bfc  jnz     loc_180011CC0
0x180011c02  mov     [rax], rdx
0x180011c05  mov     [rdx+8], rax
0x180011c09  mov     [rcx+8], rcx
0x180011c0d  mov     [rcx], rcx
0x180011c10  mov     rsi, [rbx+20h]
0x180011c14  test    rsi, rsi
0x180011c17  jz      short loc_180011C94
0x180011c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c20  cmp     rcx, r14
0x180011c23  jz      short loc_180011C76
0x180011c25  test    byte ptr [rcx+1Ch], 80h
0x180011c29  jz      short loc_180011C76
0x180011c2b  cmp     byte ptr [rcx+19h], 4
0x180011c2f  jb      short loc_180011C76
0x180011c31  mov     rax, [rsi+40h]
0x180011c35  mov     r11, rsi
0x180011c38  mov     r8, [rdi+88h]
0x180011c3f  not     r11
0x180011c42  mov     rcx, [rcx+10h]
0x180011c46  not     r8
0x180011c49  mov     [rsp+78h+var_40], rax
0x180011c4e  mov     r10, rbx
0x180011c51  mov     [rsp+78h+var_48], r11
0x180011c56  not     r10
0x180011c59  mov     [rsp+78h+var_50], r10
0x180011c5e  mov     r9, rdi
0x180011c61  mov     [rsp+78h+var_58], r8
0x180011c66  not     r9
0x180011c69  mov     r8, r15
0x180011c6c  mov     edx, 23h ; '#'
0x180011c71  call    WPP_SF_qqqqi
0x180011c76  mov     rcx, rbx; this
0x180011c79  call    ?RemoveIpcLink@ApfCircuit@Apx@@QEAAXXZ; Apx::ApfCircuit::RemoveIpcLink(void)
0x180011c7e  mov     rcx, [rdi+88h]
0x180011c85  mov     rdx, rsi
0x180011c88  mov     rax, [rcx]
0x180011c8b  mov     rax, [rax+38h]
0x180011c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c94  lea     rax, aOnecoreuapDriv_3; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180011c9b  not     rbx
0x180011c9e  mov     rdx, rbx; Apx::ApfVerify *
0x180011ca1  mov     [rsp+78h+var_58], rax
0x180011ca6  mov     r9d, 1D8h
0x180011cac  mov     r8d, 44787041h
0x180011cb2  xor     ecx, ecx; this
0x180011cb4  call    imp_ApxObjectDereferenceActual
0x180011cb9  xor     esi, esi
0x180011cbb  jmp     loc_180011BAA
0x180011cc0  mov     ecx, 3
0x180011cc5  int     29h; Win8: RtlFailFast(ecx)
```

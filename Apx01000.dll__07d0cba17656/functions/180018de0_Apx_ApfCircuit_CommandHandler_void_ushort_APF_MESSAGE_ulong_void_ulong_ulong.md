# Apx::ApfCircuit::_CommandHandler(void *,ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)

- ea: `0x180018de0`
- end: `0x180018ff5`
- name: `?_CommandHandler@ApfCircuit@Apx@@CAJPEAXGPEAUAPF_MESSAGE@@K0KPEAK@Z`
- size: `533`
- prototype: `__int64 __fastcall(Apx::ApfCircuit *this, unsigned __int16, struct APF_MESSAGE *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a12c`
- `0x18000b008`
- `0x180017a08`
- `0x180018de0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuit::_CommandHandler(
        Apx::ApfCircuit *this,
        unsigned __int16 a2,
        struct APF_MESSAGE *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  int v8; // esi
  unsigned __int16 v11; // r11
  unsigned int v12; // edi
  __int64 v13; // rax
  unsigned int v14; // r8d
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx

  v8 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  }
  v11 = *((_WORD *)a3 + 13);
  *a7 = 0;
  if ( v8 == 1 )
  {
    v18 = Apx::ApfCircuit::CircuitHandler(this, v11, a3, a4, a5, a6, a7);
    goto LABEL_24;
  }
  if ( v8 == 3 )
  {
    LODWORD(v13) = *((_DWORD *)a3 + 10);
    v14 = *((_DWORD *)this + 140);
    if ( (unsigned int)v13 >= v14 )
    {
      v12 = -1073741811;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v12;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      v16 = 12;
      goto LABEL_14;
    }
    _mm_lfence();
    v19 = *(_QWORD *)(*((_QWORD *)this + 69) + 8LL * *((unsigned int *)a3 + 10));
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct APF_MESSAGE *, _QWORD, void *, unsigned int, unsigned int *))(*(_QWORD *)v19 + 16LL))(
            v19,
            v11,
            a3,
            a4,
            a5,
            a6,
            a7);
LABEL_24:
    v12 = v18;
    goto LABEL_25;
  }
  if ( v8 != 4 )
  {
    v12 = -1073741811;
LABEL_25:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v13 = *((unsigned int *)a3 + 10);
  v14 = *((_DWORD *)this + 144);
  if ( (unsigned int)v13 < v14 )
  {
    _mm_lfence();
    v17 = *(_QWORD *)(*((_QWORD *)this + 71) + 8 * v13);
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct APF_MESSAGE *, _QWORD, void *, unsigned int, unsigned int *))(*(_QWORD *)v17 + 16LL))(
            v17,
            v11,
            a3,
            a4,
            a5,
            a6,
            a7);
    goto LABEL_24;
  }
  v12 = -1073741811;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 11;
LABEL_14:
    WPP_SF_qddd(
      v15[2],
      v16,
      &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids,
      ~(unsigned __int64)this,
      v13,
      v14,
      -1073741811);
    goto LABEL_25;
  }
LABEL_26:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(v15[2], 13, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  return v12;
}

```

## disassembly

```asm
0x180018de0  push    rbx
0x180018de2  push    rbp
0x180018de3  push    rsi
0x180018de4  push    rdi
0x180018de5  push    r14
0x180018de7  sub     rsp, 40h
0x180018deb  mov     ebp, r9d
0x180018dee  movzx   esi, dx
0x180018df1  mov     rdi, r8
0x180018df4  mov     rbx, rcx
0x180018df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dfe  lea     r14, WPP_GLOBAL_Control
0x180018e05  cmp     rcx, r14
0x180018e08  jz      short loc_180018E2B
0x180018e0a  test    byte ptr [rcx+1Ch], 1
0x180018e0e  jz      short loc_180018E2B
0x180018e10  cmp     byte ptr [rcx+19h], 5
0x180018e14  jb      short loc_180018E2B
0x180018e16  mov     rcx, [rcx+10h]
0x180018e1a  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018e21  mov     edx, 0Ah
0x180018e26  call    WPP_SF_
0x180018e2b  mov     rdx, [rsp+68h+arg_30]
0x180018e33  mov     ecx, esi
0x180018e35  movzx   r11d, word ptr [rdi+1Ah]
0x180018e3a  mov     dword ptr [rdx], 0
0x180018e40  sub     ecx, 1
0x180018e43  jz      loc_180018F8A
0x180018e49  sub     ecx, 2
0x180018e4c  jz      loc_180018F12
0x180018e52  cmp     ecx, 1
0x180018e55  jz      short loc_180018E61
0x180018e57  mov     edi, 0C000000Dh
0x180018e5c  jmp     loc_180018FBB
0x180018e61  mov     eax, [rdi+28h]
0x180018e64  mov     r8d, [rbx+240h]
0x180018e6b  cmp     eax, r8d
0x180018e6e  jb      short loc_180018EC6
0x180018e70  mov     edi, 0C000000Dh
0x180018e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e7c  cmp     rcx, r14
0x180018e7f  jz      loc_180018FE8
0x180018e85  test    byte ptr [rcx+1Ch], 20h
0x180018e89  jz      loc_180018FC2
0x180018e8f  cmp     byte ptr [rcx+19h], 2
0x180018e93  jb      loc_180018FC2
0x180018e99  mov     edx, 0Bh
0x180018e9e  mov     rcx, [rcx+10h]
0x180018ea2  not     rbx
0x180018ea5  mov     dword ptr [rsp+68h+var_38], edi
0x180018ea9  mov     r9, rbx
0x180018eac  mov     [rsp+68h+var_40], r8d
0x180018eb1  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018eb8  mov     dword ptr [rsp+68h+var_48], eax
0x180018ebc  call    WPP_SF_qddd
0x180018ec1  jmp     loc_180018FBB
0x180018ec6  lfence
0x180018ec9  mov     rcx, rax
0x180018ecc  mov     [rsp+68h+var_38], rdx
0x180018ed1  mov     rax, [rbx+238h]
0x180018ed8  mov     rcx, [rax+rcx*8]
0x180018edc  mov     rax, [rcx]
0x180018edf  mov     r10, [rax+10h]
0x180018ee3  mov     eax, [rsp+68h+arg_28]
0x180018eea  mov     [rsp+68h+var_40], eax
0x180018eee  mov     rax, [rsp+68h+arg_20]
0x180018ef6  mov     [rsp+68h+var_48], rax
0x180018efb  mov     rax, r10
0x180018efe  movzx   edx, r11w
0x180018f02  mov     r8, rdi
0x180018f05  mov     r9d, ebp
0x180018f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f0d  jmp     loc_180018FB9
0x180018f12  mov     eax, [rdi+28h]
0x180018f15  mov     r8d, [rbx+230h]
0x180018f1c  cmp     eax, r8d
0x180018f1f  jb      short loc_180018F50
0x180018f21  mov     edi, 0C000000Dh
0x180018f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f2d  cmp     rcx, r14
0x180018f30  jz      loc_180018FE8
0x180018f36  test    byte ptr [rcx+1Ch], 20h
0x180018f3a  jz      loc_180018FC2
0x180018f40  cmp     byte ptr [rcx+19h], 2
0x180018f44  jb      short loc_180018FC2
0x180018f46  mov     edx, 0Ch
0x180018f4b  jmp     loc_180018E9E
0x180018f50  lfence
0x180018f53  mov     rcx, rax
0x180018f56  mov     [rsp+68h+var_38], rdx
0x180018f5b  mov     rax, [rbx+228h]
0x180018f62  mov     edx, [rsp+68h+arg_28]
0x180018f69  mov     [rsp+68h+var_40], edx
0x180018f6d  mov     rdx, [rsp+68h+arg_20]
0x180018f75  mov     rcx, [rax+rcx*8]
0x180018f79  mov     [rsp+68h+var_48], rdx
0x180018f7e  mov     rax, [rcx]
0x180018f81  mov     rax, [rax+10h]
0x180018f85  jmp     loc_180018EFE
0x180018f8a  mov     eax, [rsp+68h+arg_28]
0x180018f91  mov     r9d, ebp; unsigned int
0x180018f94  mov     [rsp+68h+var_38], rdx; unsigned int *
0x180018f99  mov     r8, rdi; struct APF_MESSAGE *
0x180018f9c  mov     [rsp+68h+var_40], eax; unsigned int
0x180018fa0  movzx   edx, r11w; unsigned __int16
0x180018fa4  mov     rax, [rsp+68h+arg_20]
0x180018fac  mov     rcx, rbx; this
0x180018faf  mov     [rsp+68h+var_48], rax; void *
0x180018fb4  call    ?CircuitHandler@ApfCircuit@Apx@@AEAAJGPEAUAPF_MESSAGE@@KPEAXKPEAK@Z; Apx::ApfCircuit::CircuitHandler(ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)
0x180018fb9  mov     edi, eax
0x180018fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fc2  cmp     rcx, r14
0x180018fc5  jz      short loc_180018FE8
0x180018fc7  test    byte ptr [rcx+1Ch], 1
0x180018fcb  jz      short loc_180018FE8
0x180018fcd  cmp     byte ptr [rcx+19h], 5
0x180018fd1  jb      short loc_180018FE8
0x180018fd3  mov     rcx, [rcx+10h]
0x180018fd7  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018fde  mov     edx, 0Dh
0x180018fe3  call    WPP_SF_
0x180018fe8  mov     eax, edi
0x180018fea  add     rsp, 40h
0x180018fee  pop     r14
0x180018ff0  pop     rdi
0x180018ff1  pop     rsi
0x180018ff2  pop     rbp
0x180018ff3  pop     rbx
0x180018ff4  retn
```

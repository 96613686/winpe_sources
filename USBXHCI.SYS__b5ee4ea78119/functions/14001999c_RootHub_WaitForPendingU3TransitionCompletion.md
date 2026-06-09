# RootHub_WaitForPendingU3TransitionCompletion

- ea: `0x14001999c`
- end: `0x140019cef`
- name: `RootHub_WaitForPendingU3TransitionCompletion`
- size: `851`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140018514`
- `0x14001d1d0`
- `0x14001fe00`

## callees

- `0x140002568`
- `0x14001999c`
- `0x140019cf8`
- `0x140019d6c`
- `0x14001d118`
- `0x14001f830`
- `0x140021830`
- `0x140021964`
- `0x140037d3c`

## import_xrefs

- `HAL!KeStallExecutionProcessor` at `0x140019a0f`
- `HAL!KeStallExecutionProcessor` at `0x140019a0f`

## pseudocode

```c
__int64 __fastcall RootHub_WaitForPendingU3TransitionCompletion(_QWORD *a1, int a2, char a3)
{
  char v3; // r9
  unsigned int v4; // r8d
  unsigned int v5; // ebp
  __int64 v8; // r13
  unsigned int v9; // r15d
  unsigned int *v10; // r12
  int v11; // edi
  unsigned int v12; // eax
  int v13; // edx
  unsigned int v14; // ebx
  char v15; // cl
  void *v16; // r10
  int Ulong; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // ebx
  int v22; // r9d
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+80h] [rbp+8h]

  v3 = a3;
  v4 = a2 - 1;
  v5 = 0;
  v8 = *(_QWORD *)(a1[1] + 88LL);
  v9 = -1073741823;
  v10 = (unsigned int *)(a1[5] + 16LL * (unsigned int)(a2 - 1));
  v11 = -1;
  v26 = (unsigned int)(a2 - 1);
  while ( 1 )
  {
    if ( v3 && v5 && v5 == 3 * (v5 / 3) )
    {
      RootHub_AcquireReadModifyWriteLock(a1, v4);
      Ulong = XilRegister_ReadUlong(v8, v10);
      v21 = Ulong & 0xE00C200 | 0x10060;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dDD(*(_QWORD *)(a1[1] + 72LL), v19, v20, 241, v25, a2, Ulong, 96);
      XilRegister_WriteUlong(v8, v10, v21);
      RootHub_ReleaseReadModifyWriteLock(a1, (unsigned int)(a2 - 1));
    }
    v12 = XilRegister_ReadUlong(v8, v10);
    v14 = v12;
    if ( v12 == -1 )
      break;
    if ( v12 == v11 )
      goto LABEL_5;
    v15 = *(_BYTE *)(120 * v26 + a1[6] + 13);
    if ( v15 != 2 )
    {
      if ( v15 != 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(a1[1] + 72LL),
            v13,
            11,
            244,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            a2,
            v12);
        }
        v9 = 0;
        break;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_9;
      v22 = 243;
      goto LABEL_22;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = 242;
LABEL_22:
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        v22,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        a2,
        v12);
    }
LABEL_9:
    if ( !(unsigned __int8)RootHub_IsPortU3TransitionPending(120 * v26 + a1[6], v14) )
    {
      v9 = 0;
      break;
    }
    v11 = v14;
    if ( WPP_RECORDER_INITIALIZED != v16 )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        245,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        a2,
        v5);
    }
LABEL_5:
    KeStallExecutionProcessor(0xAu);
    if ( ++v5 >= 0x1900 )
      break;
    v3 = a3;
    v4 = a2 - 1;
  }
  if ( v5 == 6400 )
  {
    v23 = a1[1];
    ++*(_DWORD *)(v23 + 892);
    ++*(_DWORD *)(v23 + 960);
    *(_BYTE *)(v23 + 872) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        246,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        a2,
        v14);
    }
  }
  else if ( v5 )
  {
    if ( v5 > 0x960 )
    {
      v24 = a1[1];
      ++*(_DWORD *)(v24 + 896);
      ++*(_DWORD *)(v24 + 964);
      *(_BYTE *)(v24 + 872) = 1;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        247,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v5,
        a2);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14001999c  mov     [rsp+arg_8], rbx
0x1400199a1  mov     [rsp+arg_10], r8b
0x1400199a6  push    rbp
0x1400199a7  push    rsi
0x1400199a8  push    rdi
0x1400199a9  push    r12
0x1400199ab  push    r13
0x1400199ad  push    r14
0x1400199af  push    r15
0x1400199b1  sub     rsp, 40h
0x1400199b5  mov     rax, [rcx+8]
0x1400199b9  mov     r9b, r8b
0x1400199bc  lea     r8d, [rdx-1]
0x1400199c0  xor     ebp, ebp
0x1400199c2  mov     r12d, r8d
0x1400199c5  mov     r14d, edx
0x1400199c8  shl     r12, 4
0x1400199cc  mov     rsi, rcx
0x1400199cf  mov     r13, [rax+58h]
0x1400199d3  mov     r15d, 0C0000001h
0x1400199d9  add     r12, [rcx+28h]
0x1400199dd  mov     eax, r8d
0x1400199e0  or      edi, 0FFFFFFFFh
0x1400199e3  mov     [rsp+78h+arg_0], rax
0x1400199eb  test    r9b, r9b
0x1400199ee  jnz     loc_140019AB1
0x1400199f4  mov     rdx, r12
0x1400199f7  mov     rcx, r13
0x1400199fa  call    XilRegister_ReadUlong
0x1400199ff  mov     ebx, eax
0x140019a01  cmp     eax, 0FFFFFFFFh
0x140019a04  jz      short loc_140019A7A
0x140019a06  cmp     eax, edi
0x140019a08  jnz     short loc_140019A33
0x140019a0a  mov     ecx, 0Ah; MicroSeconds
0x140019a0f  call    cs:__imp_KeStallExecutionProcessor
0x140019a16  nop     dword ptr [rax+rax+00h]
0x140019a1b  inc     ebp
0x140019a1d  cmp     ebp, 1900h
0x140019a23  jnb     short loc_140019A7A
0x140019a25  mov     r9b, [rsp+78h+arg_10]
0x140019a2d  lea     r8d, [r14-1]
0x140019a31  jmp     short loc_1400199EB
0x140019a33  imul    rdi, [rsp+78h+arg_0], 78h ; 'x'
0x140019a3c  mov     rax, [rsi+30h]
0x140019a40  mov     cl, [rdi+rax+0Dh]
0x140019a44  cmp     cl, 2
0x140019a47  jnz     loc_140019B24
0x140019a4d  lea     r10, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019a54  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x140019a5b  jnz     loc_140019C2A
0x140019a61  mov     rcx, [rsi+30h]
0x140019a65  mov     edx, ebx
0x140019a67  add     rcx, rdi
0x140019a6a  call    RootHub_IsPortU3TransitionPending
0x140019a6f  test    al, al
0x140019a71  jnz     loc_140019BC1
0x140019a77  xor     r15d, r15d
0x140019a7a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140019a81  cmp     ebp, 1900h
0x140019a87  jz      loc_140019C35
0x140019a8d  test    ebp, ebp
0x140019a8f  jnz     loc_140019C8E
0x140019a95  mov     rbx, [rsp+78h+arg_8]
0x140019a9d  mov     eax, r15d
0x140019aa0  add     rsp, 40h
0x140019aa4  pop     r15
0x140019aa6  pop     r14
0x140019aa8  pop     r13
0x140019aaa  pop     r12
0x140019aac  pop     rdi
0x140019aad  pop     rsi
0x140019aae  pop     rbp
0x140019aaf  retn
0x140019ab1  test    ebp, ebp
0x140019ab3  jz      loc_1400199F4
0x140019ab9  mov     eax, 0AAAAAAABh
0x140019abe  mul     ebp
0x140019ac0  shr     edx, 1
0x140019ac2  lea     ecx, [rdx+rdx*2]
0x140019ac5  cmp     ebp, ecx
0x140019ac7  jnz     loc_1400199F4
0x140019acd  mov     edx, r8d
0x140019ad0  mov     rcx, rsi
0x140019ad3  call    RootHub_AcquireReadModifyWriteLock
0x140019ad8  mov     rdx, r12
0x140019adb  mov     rcx, r13
0x140019ade  call    XilRegister_ReadUlong
0x140019ae3  mov     ebx, eax
0x140019ae5  and     ebx, 0E00C200h
0x140019aeb  or      ebx, 10060h
0x140019af1  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019af8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140019aff  jnz     loc_140019C05
0x140019b05  mov     r8d, ebx
0x140019b08  mov     rdx, r12
0x140019b0b  mov     rcx, r13
0x140019b0e  call    XilRegister_WriteUlong
0x140019b13  lea     edx, [r14-1]
0x140019b17  mov     rcx, rsi
0x140019b1a  call    RootHub_ReleaseReadModifyWriteLock
0x140019b1f  jmp     loc_1400199F4
0x140019b24  cmp     cl, 3
0x140019b27  jnz     short loc_140019B79
0x140019b29  lea     r10, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019b30  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x140019b37  jz      loc_140019A61
0x140019b3d  mov     r9d, 0F3h
0x140019b43  mov     rcx, [rsi+8]
0x140019b47  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140019b4e  mov     [rsp+78h+var_48], ebx
0x140019b52  mov     r8d, 0Bh
0x140019b58  mov     [rsp+78h+var_50], r14d
0x140019b5d  mov     dl, 4
0x140019b5f  mov     [rsp+78h+var_58], rax
0x140019b64  mov     rcx, [rcx+48h]
0x140019b68  call    WPP_RECORDER_SF_dD
0x140019b6d  lea     r10, WPP_RECORDER_INITIALIZED
0x140019b74  jmp     loc_140019A61
0x140019b79  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019b80  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140019b87  jz      short loc_140019BB9
0x140019b89  mov     rcx, [rsi+8]
0x140019b8d  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140019b94  mov     [rsp+78h+var_48], ebx
0x140019b98  mov     r9d, 0F4h
0x140019b9e  mov     [rsp+78h+var_50], r14d
0x140019ba3  mov     r8d, 0Bh
0x140019ba9  mov     dl, 2
0x140019bab  mov     [rsp+78h+var_58], rax
0x140019bb0  mov     rcx, [rcx+48h]
0x140019bb4  call    WPP_RECORDER_SF_dD
0x140019bb9  xor     r15d, r15d
0x140019bbc  jmp     loc_140019A81
0x140019bc1  mov     edi, ebx
0x140019bc3  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x140019bca  jz      loc_140019A0A
0x140019bd0  mov     rcx, [rsi+8]
0x140019bd4  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140019bdb  mov     [rsp+78h+var_48], ebp
0x140019bdf  mov     r9d, 0F5h
0x140019be5  mov     [rsp+78h+var_50], r14d
0x140019bea  mov     r8d, 0Bh
0x140019bf0  mov     dl, 4
0x140019bf2  mov     [rsp+78h+var_58], rax
0x140019bf7  mov     rcx, [rcx+48h]
0x140019bfb  call    WPP_RECORDER_SF_DD
0x140019c00  jmp     loc_140019A0A
0x140019c05  mov     rcx, [rsi+8]
0x140019c09  mov     r9d, 0F1h
0x140019c0f  mov     [rsp+78h+var_40], ebx
0x140019c13  mov     [rsp+78h+var_48], eax
0x140019c17  mov     [rsp+78h+var_50], r14d
0x140019c1c  mov     rcx, [rcx+48h]
0x140019c20  call    WPP_RECORDER_SF_dDD
0x140019c25  jmp     loc_140019B05
0x140019c2a  mov     r9d, 0F2h
0x140019c30  jmp     loc_140019B43
0x140019c35  mov     rax, [rsi+8]
0x140019c39  inc     dword ptr [rax+37Ch]
0x140019c3f  inc     dword ptr [rax+3C0h]
0x140019c45  mov     byte ptr [rax+368h], 1
0x140019c4c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140019c53  jz      loc_140019A95
0x140019c59  mov     rcx, [rsi+8]
0x140019c5d  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140019c64  mov     [rsp+78h+var_48], ebx
0x140019c68  mov     r9d, 0F6h
0x140019c6e  mov     [rsp+78h+var_50], r14d
0x140019c73  mov     r8d, 0Bh
0x140019c79  mov     dl, 2
0x140019c7b  mov     [rsp+78h+var_58], rax
0x140019c80  mov     rcx, [rcx+48h]
0x140019c84  call    WPP_RECORDER_SF_dD
0x140019c89  jmp     loc_140019A95
0x140019c8e  cmp     ebp, 960h
0x140019c94  jbe     short loc_140019CAD
0x140019c96  mov     rax, [rsi+8]
0x140019c9a  inc     dword ptr [rax+380h]
0x140019ca0  inc     dword ptr [rax+3C4h]
0x140019ca6  mov     byte ptr [rax+368h], 1
0x140019cad  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140019cb4  jz      loc_140019A95
0x140019cba  mov     rcx, [rsi+8]
0x140019cbe  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140019cc5  mov     [rsp+78h+var_48], r14d
0x140019cca  mov     r9d, 0F7h
0x140019cd0  mov     [rsp+78h+var_50], ebp
0x140019cd4  mov     r8d, 0Bh
0x140019cda  mov     dl, 4
0x140019cdc  mov     [rsp+78h+var_58], rax
0x140019ce1  mov     rcx, [rcx+48h]
0x140019ce5  call    WPP_RECORDER_SF_DD
0x140019cea  jmp     loc_140019A95
```

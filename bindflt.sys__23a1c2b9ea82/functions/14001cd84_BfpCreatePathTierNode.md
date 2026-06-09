# BfpCreatePathTierNode

- ea: `0x14001cd84`
- end: `0x14001d127`
- name: `BfpCreatePathTierNode`
- size: `931`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140019c44`
- `0x14001b280`

## callees

- `0x140001348`
- `0x140003304`
- `0x14001cd84`
- `0x14001d130`
- `0x14001d194`
- `0x14001e854`
- `0x140020180`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ce1f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ced4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001d032`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ce1f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ced4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001d032`
- `ntoskrnl!ExAllocatePool2` at `0x14001cdc0`
- `ntoskrnl!ExAllocatePool2` at `0x14001cdc0`

## pseudocode

```c
__int64 __fastcall BfpCreatePathTierNode(
        PCUNICODE_STRING SourceString,
        int a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        volatile signed __int64 *a7,
        __int64 a8,
        _QWORD *a9)
{
  unsigned int v12; // r13d
  __int64 Pool2; // rax
  int v14; // edx
  char *v15; // rdi
  int UnicodeString; // ebx
  int v18; // edx
  int v19; // eax
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  int v22; // r9d
  char v23; // [rsp+30h] [rbp-68h]
  char v24; // [rsp+38h] [rbp-60h]
  UNICODE_STRING SourceStringa; // [rsp+40h] [rbp-58h] BYREF

  v12 = a4;
  *a9 = 0;
  Pool2 = ExAllocatePool2(256, 96, 1886209602, a4);
  v15 = (char *)Pool2;
  if ( Pool2 )
  {
    UnicodeString = BfAllocateUnicodeString(SourceString->MaximumLength, Pool2 + 32);
    if ( UnicodeString < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = UnicodeString;
        v22 = 20;
        v23 = 62;
        goto LABEL_29;
      }
      goto LABEL_24;
    }
    RtlCopyUnicodeString((PUNICODE_STRING)v15 + 2, SourceString);
    *(_DWORD *)v15 = a2;
    *((_QWORD *)v15 + 11) = 0;
    if ( a3 )
    {
      v21 = v15 + 80;
      if ( (a2 & 0xA) != 0 )
      {
        *v21 = a8;
      }
      else
      {
        UnicodeString = BfpCreatePathTree(v21);
        if ( UnicodeString < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v24 = UnicodeString;
            v22 = 21;
            v23 = 91;
LABEL_29:
            LOBYTE(v18) = 2;
            WPP_RECORDER_SF_sDd(
              WPP_GLOBAL_Control->DeviceExtension,
              v18,
              8,
              v22,
              (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
              v23,
              v24);
            goto LABEL_24;
          }
          goto LABEL_24;
        }
      }
    }
    if ( (a2 & 1) != 0 )
    {
      if ( (a2 & 2) != 0 )
      {
        if ( _InterlockedIncrement64(a7) <= 1 )
          __fastfail(0xEu);
        *((_QWORD *)v15 + 9) = a7;
        UnicodeString = BfAllocateUnicodeString(SourceString->MaximumLength, a7 + 4);
        if ( UnicodeString >= 0 )
        {
          RtlCopyUnicodeString((PUNICODE_STRING)(*((_QWORD *)v15 + 9) + 32LL), SourceString);
          goto LABEL_15;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v24 = UnicodeString;
          v22 = 22;
          v23 = 121;
          goto LABEL_29;
        }
        goto LABEL_24;
      }
      v19 = *(_DWORD *)(a5 + 24);
      if ( v19 == 6 || v19 == 13 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            8,
            23,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            135);
        }
        UnicodeString = -1073741637;
        goto LABEL_24;
      }
      UnicodeString = BfpCreateMappingInformation(a6, v12, v15 + 72);
      if ( UnicodeString < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_24;
        v24 = UnicodeString;
        v22 = 24;
        v23 = -110;
        goto LABEL_29;
      }
    }
    else if ( (a2 & 2) != 0 || (a2 & 4) == 0 )
    {
      goto LABEL_15;
    }
    v20 = *(unsigned __int16 *)(a6 + 4);
    *(_DWORD *)(&SourceStringa.MaximumLength + 1) = 0;
    SourceStringa.Length = v20;
    SourceStringa.MaximumLength = v20;
    SourceStringa.Buffer = (PWSTR)(a6 + 6);
    UnicodeString = BfAllocateUnicodeString(v20, v15 + 56);
    if ( UnicodeString >= 0 )
    {
      RtlCopyUnicodeString((PUNICODE_STRING)(v15 + 56), &SourceStringa);
      *((_QWORD *)v15 + 6) = *(_QWORD *)a5;
LABEL_15:
      *a9 = v15;
      return 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = UnicodeString;
      v22 = 25;
      v23 = -93;
      goto LABEL_29;
    }
LABEL_24:
    BfpDeletePathTierNode(v15);
    return (unsigned int)UnicodeString;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      8,
      19,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      53);
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14001cd84  push    rbx
0x14001cd86  push    rbp
0x14001cd87  push    rsi
0x14001cd88  push    rdi
0x14001cd89  push    r12
0x14001cd8b  push    r13
0x14001cd8d  push    r14
0x14001cd8f  push    r15
0x14001cd91  sub     rsp, 58h
0x14001cd95  mov     r12, [rsp+98h+arg_40]
0x14001cd9d  mov     r15b, r8b
0x14001cda0  mov     esi, edx
0x14001cda2  mov     rbp, rcx
0x14001cda5  mov     edx, 60h ; '`'
0x14001cdaa  mov     ecx, 100h
0x14001cdaf  mov     r8d, 706D4642h
0x14001cdb5  mov     r13d, r9d
0x14001cdb8  mov     qword ptr [r12], 0
0x14001cdc0  call    cs:__imp_ExAllocatePool2
0x14001cdc7  nop     dword ptr [rax+rax+00h]
0x14001cdcc  mov     rdi, rax
0x14001cdcf  test    rax, rax
0x14001cdd2  jnz     short loc_14001CE01
0x14001cdd4  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cddb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cde2  jnz     loc_14001D0AF
0x14001cde8  mov     ebx, 0C000009Ah
0x14001cded  mov     eax, ebx
0x14001cdef  add     rsp, 58h
0x14001cdf3  pop     r15
0x14001cdf5  pop     r14
0x14001cdf7  pop     r13
0x14001cdf9  pop     r12
0x14001cdfb  pop     rdi
0x14001cdfc  pop     rsi
0x14001cdfd  pop     rbp
0x14001cdfe  pop     rbx
0x14001cdff  retn
0x14001ce01  movzx   ecx, word ptr [rbp+2]
0x14001ce05  lea     rdx, [rax+20h]
0x14001ce09  call    BfAllocateUnicodeString
0x14001ce0e  mov     ebx, eax
0x14001ce10  test    eax, eax
0x14001ce12  js      loc_14001CF3E
0x14001ce18  mov     rdx, rbp; SourceString
0x14001ce1b  lea     rcx, [rdi+20h]; DestinationString
0x14001ce1f  call    cs:__imp_RtlCopyUnicodeString
0x14001ce26  nop     dword ptr [rax+rax+00h]
0x14001ce2b  mov     [rdi], esi
0x14001ce2d  mov     qword ptr [rdi+58h], 0
0x14001ce35  test    r15b, r15b
0x14001ce38  jnz     loc_14001CEF2
0x14001ce3e  mov     r15, [rsp+98h+arg_28]
0x14001ce46  mov     eax, esi
0x14001ce48  mov     r14, [rsp+98h+arg_20]
0x14001ce50  and     eax, 2
0x14001ce53  mov     ecx, 1
0x14001ce58  test    cl, sil
0x14001ce5b  jz      loc_14001CF2F
0x14001ce61  test    eax, eax
0x14001ce63  jnz     loc_14001CFF4
0x14001ce69  mov     eax, [r14+18h]
0x14001ce6d  cmp     eax, 6
0x14001ce70  jz      loc_14001CFD6
0x14001ce76  cmp     eax, 0Dh
0x14001ce79  jz      loc_14001CFD6
0x14001ce7f  lea     r8, [rdi+48h]
0x14001ce83  mov     edx, r13d
0x14001ce86  mov     rcx, r15
0x14001ce89  call    BfpCreateMappingInformation
0x14001ce8e  mov     ebx, eax
0x14001ce90  test    eax, eax
0x14001ce92  js      loc_14001D0FC
0x14001ce98  movzx   ecx, word ptr [r15+4]
0x14001ce9d  lea     rax, [r15+6]
0x14001cea1  xorps   xmm0, xmm0
0x14001cea4  lea     rdx, [rdi+38h]
0x14001cea8  movups  xmmword ptr [rsp+98h+SourceString.Length], xmm0
0x14001cead  mov     [rsp+98h+SourceString.Length], cx
0x14001ceb2  mov     [rsp+98h+SourceString.MaximumLength], cx
0x14001ceb7  mov     [rsp+98h+SourceString.Buffer], rax
0x14001cebc  call    BfAllocateUnicodeString
0x14001cec1  mov     ebx, eax
0x14001cec3  test    eax, eax
0x14001cec5  js      loc_14001CF6B
0x14001cecb  lea     rdx, [rsp+98h+SourceString]; SourceString
0x14001ced0  lea     rcx, [rdi+38h]; DestinationString
0x14001ced4  call    cs:__imp_RtlCopyUnicodeString
0x14001cedb  nop     dword ptr [rax+rax+00h]
0x14001cee0  mov     rax, [r14]
0x14001cee3  mov     [rdi+30h], rax
0x14001cee7  mov     [r12], rdi
0x14001ceeb  xor     ebx, ebx
0x14001ceed  jmp     loc_14001CDED
0x14001cef2  lea     rcx, [rdi+50h]
0x14001cef6  test    sil, 0Ah
0x14001cefa  jnz     short loc_14001CF5B
0x14001cefc  call    BfpCreatePathTree
0x14001cf01  mov     ebx, eax
0x14001cf03  test    eax, eax
0x14001cf05  jns     loc_14001CE3E
0x14001cf0b  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cf12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cf19  jz      short loc_14001CF4E
0x14001cf1b  mov     dword ptr [rsp+98h+var_60], ebx
0x14001cf1f  mov     r9d, 15h
0x14001cf25  mov     dword ptr [rsp+98h+var_68], 45Bh
0x14001cf2d  jmp     short loc_14001CFA1
0x14001cf2f  test    eax, eax
0x14001cf31  jnz     short loc_14001CEE7
0x14001cf33  test    sil, 4
0x14001cf37  jz      short loc_14001CEE7
0x14001cf39  jmp     loc_14001CE98
0x14001cf3e  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cf45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cf4c  jnz     short loc_14001CF8F
0x14001cf4e  mov     rcx, rdi; P
0x14001cf51  call    BfpDeletePathTierNode
0x14001cf56  jmp     loc_14001CDED
0x14001cf5b  mov     rax, [rsp+98h+arg_38]
0x14001cf63  mov     [rcx], rax
0x14001cf66  jmp     loc_14001CE3E
0x14001cf6b  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cf72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cf79  jz      short loc_14001CF4E
0x14001cf7b  mov     dword ptr [rsp+98h+var_60], ebx
0x14001cf7f  mov     r9d, 19h
0x14001cf85  mov     dword ptr [rsp+98h+var_68], 4A3h
0x14001cf8d  jmp     short loc_14001CFA1
0x14001cf8f  mov     dword ptr [rsp+98h+var_60], ebx
0x14001cf93  mov     r9d, 14h
0x14001cf99  mov     dword ptr [rsp+98h+var_68], 43Eh
0x14001cfa1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cfa8  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001cfaf  mov     [rsp+98h+var_70], rax
0x14001cfb4  mov     r8d, 8
0x14001cfba  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001cfc1  mov     dl, 2
0x14001cfc3  mov     [rsp+98h+var_78], rax
0x14001cfc8  mov     rcx, [rcx+40h]
0x14001cfcc  call    WPP_RECORDER_SF_sDd
0x14001cfd1  jmp     loc_14001CF4E
0x14001cfd6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cfdd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cfe4  jnz     loc_14001D06E
0x14001cfea  mov     ebx, 0C00000BBh
0x14001cfef  jmp     loc_14001CF4E
0x14001cff4  mov     rdx, [rsp+98h+arg_30]
0x14001cffc  mov     rax, rcx
0x14001cfff  lock xadd [rdx], rax
0x14001d004  add     rax, rcx
0x14001d007  cmp     rax, rcx
0x14001d00a  jle     loc_14001D0F0
0x14001d010  mov     [rdi+48h], rdx
0x14001d014  add     rdx, 20h ; ' '
0x14001d018  movzx   ecx, word ptr [rbp+2]
0x14001d01c  call    BfAllocateUnicodeString
0x14001d021  mov     ebx, eax
0x14001d023  test    eax, eax
0x14001d025  js      short loc_14001D043
0x14001d027  mov     rcx, [rdi+48h]
0x14001d02b  mov     rdx, rbp; SourceString
0x14001d02e  add     rcx, 20h ; ' '; DestinationString
0x14001d032  call    cs:__imp_RtlCopyUnicodeString
0x14001d039  nop     dword ptr [rax+rax+00h]
0x14001d03e  jmp     loc_14001CEE7
0x14001d043  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d04a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d051  jz      loc_14001CF4E
0x14001d057  mov     dword ptr [rsp+98h+var_60], ebx
0x14001d05b  mov     r9d, 16h
0x14001d061  mov     dword ptr [rsp+98h+var_68], 479h
0x14001d069  jmp     loc_14001CFA1
0x14001d06e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d075  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001d07c  mov     r9d, 17h
0x14001d082  mov     dword ptr [rsp+98h+var_68], 487h
0x14001d08a  mov     [rsp+98h+var_70], rax
0x14001d08f  mov     dl, 2
0x14001d091  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001d098  mov     rcx, [rcx+40h]
0x14001d09c  lea     r8d, [r9-0Fh]
0x14001d0a0  mov     [rsp+98h+var_78], rax
0x14001d0a5  call    WPP_RECORDER_SF_sD
0x14001d0aa  jmp     loc_14001CFEA
0x14001d0af  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0b6  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001d0bd  mov     r9d, 13h
0x14001d0c3  mov     dword ptr [rsp+98h+var_68], 435h
0x14001d0cb  mov     [rsp+98h+var_70], rax
0x14001d0d0  mov     dl, 2
0x14001d0d2  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001d0d9  mov     rcx, [rcx+40h]
0x14001d0dd  lea     r8d, [r9-0Bh]
0x14001d0e1  mov     [rsp+98h+var_78], rax
0x14001d0e6  call    WPP_RECORDER_SF_sD
0x14001d0eb  jmp     loc_14001CDE8
0x14001d0f0  mov     ecx, 0Eh
0x14001d0f5  int     29h; Win8: RtlFailFast(ecx)
0x14001d0f7  jmp     loc_14001D010
0x14001d0fc  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d103  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d10a  jz      loc_14001CF4E
0x14001d110  mov     dword ptr [rsp+98h+var_60], ebx
0x14001d114  mov     r9d, 18h
0x14001d11a  mov     dword ptr [rsp+98h+var_68], 492h
0x14001d122  jmp     loc_14001CFA1
```

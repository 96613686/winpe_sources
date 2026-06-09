# KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)

- ea: `0x18004aa70`
- end: `0x18004abd0`
- name: `?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z`
- size: `352`
- prototype: `int(KSMidiOutDevice *__hidden this, void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180045460`

## callees

- `0x180005020`
- `0x180005044`
- `0x180005530`
- `0x180005e84`
- `0x180005e9c`
- `0x18000b394`
- `0x1800481b4`
- `0x18004aa70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ab3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ab82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ab3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ab82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004ab25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004ab25`

## pseudocode

```c
__int64 __fastcall KSMidiOutDevice::WritePacketMidiData(KSMidiOutDevice *this, void *a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // ebx
  _DWORD *v9; // r12
  RTL_SRWLOCK *v10; // rdi
  int v11; // ebx
  PVOID Ptr; // rcx
  int v14; // [rsp+20h] [rbp-49h]
  unsigned int v15; // [rsp+38h] [rbp-31h]
  DWORD v16[4]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v17; // [rsp+60h] [rbp-9h]
  __int128 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v19 = 0;
  *(_OWORD *)v16 = 0;
  v8 = (a3 + 11) & 0xFFFFFFFC;
  v17 = 0;
  v18 = 0;
  v9 = operator new[](v8);
  memset_0(v9, 0, v8);
  *(_BYTE *)v9 = 0;
  v9[1] = a3;
  memcpy_0(v9 + 2, a2, a3);
  v10 = (RTL_SRWLOCK *)*((_QWORD *)this + 7);
  *(_QWORD *)&v17 = 0x100000001LL;
  v16[0] = 56;
  *(_QWORD *)&v16[2] = a4;
  LODWORD(v18) = v8;
  DWORD1(v18) = v8;
  *((_QWORD *)&v18 + 1) = v9;
  if ( v10 )
  {
    AcquireSRWLockShared(v10);
    Ptr = v10[1].Ptr;
    if ( (((unsigned __int64)Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v11 = SyncIoctl(Ptr, 0x2F8013u, 0, 0, v16, v16[0], 0, v15, 0);
      ReleaseSRWLockShared(v10);
      if ( v11 >= 0 )
      {
        v11 = 0;
        goto LABEL_8;
      }
    }
    else
    {
      ReleaseSRWLockShared(v10);
      v11 = -2147024890;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v11,
      v14);
  }
  else
  {
    v11 = -2147024890;
  }
LABEL_8:
  operator delete(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004aa70  push    rbp
0x18004aa72  push    rbx
0x18004aa73  push    rsi
0x18004aa74  push    rdi
0x18004aa75  push    r12
0x18004aa77  push    r14
0x18004aa79  push    r15
0x18004aa7b  lea     rbp, [rsp-27h]
0x18004aa80  sub     rsp, 90h
0x18004aa87  mov     rax, cs:__security_cookie
0x18004aa8e  xor     rax, rsp
0x18004aa91  mov     [rbp+57h+var_38], rax
0x18004aa95  xor     eax, eax
0x18004aa97  mov     edi, r8d
0x18004aa9a  xorps   xmm0, xmm0
0x18004aa9d  mov     [rbp+57h+var_40], rax
0x18004aaa1  mov     r15, rcx
0x18004aaa4  mov     r14, r9
0x18004aaa7  mov     rsi, rdx
0x18004aaaa  lea     eax, [rdi+0Bh]
0x18004aaad  and     eax, 0FFFFFFFCh
0x18004aab0  mov     ecx, eax; unsigned __int64
0x18004aab2  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18004aab6  mov     ebx, eax
0x18004aab8  movups  [rbp+57h+var_60], xmm0
0x18004aabc  movups  [rbp+57h+var_50], xmm0
0x18004aac0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004aac5  mov     r8d, ebx; Size
0x18004aac8  xor     edx, edx; Val
0x18004aaca  mov     rcx, rax; void *
0x18004aacd  mov     r12, rax
0x18004aad0  call    memset_0
0x18004aad5  mov     byte ptr [r12], 0
0x18004aada  lea     rcx, [r12+8]; void *
0x18004aadf  mov     r8d, edi; Size
0x18004aae2  mov     [r12+4], edi
0x18004aae7  mov     rdx, rsi; Src
0x18004aaea  call    memcpy_0
0x18004aaef  mov     rdi, [r15+38h]
0x18004aaf3  mov     eax, 1
0x18004aaf8  mov     dword ptr [rbp+57h+var_60], eax
0x18004aafb  mov     dword ptr [rbp+57h+var_60+4], eax
0x18004aafe  mov     [rbp+57h+var_70], 38h ; '8'
0x18004ab05  mov     qword ptr [rbp+57h+var_70+8], r14
0x18004ab09  mov     dword ptr [rbp+57h+var_50], ebx
0x18004ab0c  mov     dword ptr [rbp+57h+var_50+4], ebx
0x18004ab0f  mov     qword ptr [rbp+57h+var_50+8], r12
0x18004ab13  test    rdi, rdi
0x18004ab16  jnz     short loc_18004AB22
0x18004ab18  mov     ebx, 80070006h
0x18004ab1d  jmp     loc_18004ABA8
0x18004ab22  mov     rcx, rdi; SRWLock
0x18004ab25  call    cs:__imp_AcquireSRWLockShared
0x18004ab2b  mov     rcx, [rdi+8]; hFile
0x18004ab2f  lea     rax, [rcx+1]
0x18004ab33  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004ab39  jnz     short loc_18004AB4B
0x18004ab3b  mov     rcx, rdi; SRWLock
0x18004ab3e  call    cs:__imp_ReleaseSRWLockShared
0x18004ab44  mov     ebx, 80070006h
0x18004ab49  jmp     short loc_18004AB8C
0x18004ab4b  mov     eax, [rbp+57h+var_70]
0x18004ab4e  xor     r9d, r9d; nInBufferSize
0x18004ab51  mov     [rsp+0C0h+var_80], 0; void *
0x18004ab5a  xor     r8d, r8d; lpInBuffer
0x18004ab5d  mov     [rsp+0C0h+lpNumberOfBytesTransferred], 0; lpNumberOfBytesTransferred
0x18004ab66  mov     edx, 2F8013h; dwIoControlCode
0x18004ab6b  mov     [rsp+0C0h+var_98], eax; DWORD
0x18004ab6f  lea     rax, [rbp+57h+var_70]
0x18004ab73  mov     [rsp+0C0h+var_A0], rax; int
0x18004ab78  call    ?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)
0x18004ab7d  mov     rcx, rdi; SRWLock
0x18004ab80  mov     ebx, eax
0x18004ab82  call    cs:__imp_ReleaseSRWLockShared
0x18004ab88  test    ebx, ebx
0x18004ab8a  jns     short loc_18004ABA6
0x18004ab8c  mov     rcx, [rbp+5Fh]; this
0x18004ab90  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004ab97  mov     r9d, ebx; char *
0x18004ab9a  mov     edx, 2DAh; void *
0x18004ab9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aba4  jmp     short loc_18004ABA8
0x18004aba6  xor     ebx, ebx
0x18004aba8  mov     rcx, r12; Block
0x18004abab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004abb0  mov     eax, ebx
0x18004abb2  mov     rcx, [rbp+57h+var_38]
0x18004abb6  xor     rcx, rsp; StackCookie
0x18004abb9  call    __security_check_cookie
0x18004abbe  add     rsp, 90h
0x18004abc5  pop     r15
0x18004abc7  pop     r14
0x18004abc9  pop     r12
0x18004abcb  pop     rdi
0x18004abcc  pop     rsi
0x18004abcd  pop     rbx
0x18004abce  pop     rbp
0x18004abcf  retn
```

# KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)

- ea: `0x18002a0d0`
- end: `0x18002a230`
- name: `?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z`
- size: `352`
- prototype: `__int64 __fastcall(KSMidiOutDevice *this, void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180029a5c`

## callees

- `0x180004410`
- `0x180004434`
- `0x180004920`
- `0x180005254`
- `0x18000526c`
- `0x18000a814`
- `0x180027650`
- `0x18002a0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a19e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a1e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a19e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a1e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a185`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a185`

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
0x18002a0d0  push    rbp
0x18002a0d2  push    rbx
0x18002a0d3  push    rsi
0x18002a0d4  push    rdi
0x18002a0d5  push    r12
0x18002a0d7  push    r14
0x18002a0d9  push    r15
0x18002a0db  lea     rbp, [rsp-27h]
0x18002a0e0  sub     rsp, 90h
0x18002a0e7  mov     rax, cs:__security_cookie
0x18002a0ee  xor     rax, rsp
0x18002a0f1  mov     [rbp+57h+var_38], rax
0x18002a0f5  xor     eax, eax
0x18002a0f7  mov     edi, r8d
0x18002a0fa  xorps   xmm0, xmm0
0x18002a0fd  mov     [rbp+57h+var_40], rax
0x18002a101  mov     r15, rcx
0x18002a104  mov     r14, r9
0x18002a107  mov     rsi, rdx
0x18002a10a  lea     eax, [rdi+0Bh]
0x18002a10d  and     eax, 0FFFFFFFCh
0x18002a110  mov     ecx, eax; unsigned __int64
0x18002a112  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18002a116  mov     ebx, eax
0x18002a118  movups  [rbp+57h+var_60], xmm0
0x18002a11c  movups  [rbp+57h+var_50], xmm0
0x18002a120  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002a125  mov     r8d, ebx; Size
0x18002a128  xor     edx, edx; Val
0x18002a12a  mov     rcx, rax; void *
0x18002a12d  mov     r12, rax
0x18002a130  call    memset_0
0x18002a135  mov     byte ptr [r12], 0
0x18002a13a  lea     rcx, [r12+8]; void *
0x18002a13f  mov     r8d, edi; Size
0x18002a142  mov     [r12+4], edi
0x18002a147  mov     rdx, rsi; Src
0x18002a14a  call    memcpy_0
0x18002a14f  mov     rdi, [r15+38h]
0x18002a153  mov     eax, 1
0x18002a158  mov     dword ptr [rbp+57h+var_60], eax
0x18002a15b  mov     dword ptr [rbp+57h+var_60+4], eax
0x18002a15e  mov     [rbp+57h+var_70], 38h ; '8'
0x18002a165  mov     qword ptr [rbp+57h+var_70+8], r14
0x18002a169  mov     dword ptr [rbp+57h+var_50], ebx
0x18002a16c  mov     dword ptr [rbp+57h+var_50+4], ebx
0x18002a16f  mov     qword ptr [rbp+57h+var_50+8], r12
0x18002a173  test    rdi, rdi
0x18002a176  jnz     short loc_18002A182
0x18002a178  mov     ebx, 80070006h
0x18002a17d  jmp     loc_18002A208
0x18002a182  mov     rcx, rdi; SRWLock
0x18002a185  call    cs:__imp_AcquireSRWLockShared
0x18002a18b  mov     rcx, [rdi+8]; hFile
0x18002a18f  lea     rax, [rcx+1]
0x18002a193  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a199  jnz     short loc_18002A1AB
0x18002a19b  mov     rcx, rdi; SRWLock
0x18002a19e  call    cs:__imp_ReleaseSRWLockShared
0x18002a1a4  mov     ebx, 80070006h
0x18002a1a9  jmp     short loc_18002A1EC
0x18002a1ab  mov     eax, [rbp+57h+var_70]
0x18002a1ae  xor     r9d, r9d; nInBufferSize
0x18002a1b1  mov     [rsp+0C0h+var_80], 0; void *
0x18002a1ba  xor     r8d, r8d; lpInBuffer
0x18002a1bd  mov     [rsp+0C0h+lpNumberOfBytesTransferred], 0; lpNumberOfBytesTransferred
0x18002a1c6  mov     edx, 2F8013h; dwIoControlCode
0x18002a1cb  mov     [rsp+0C0h+var_98], eax; DWORD
0x18002a1cf  lea     rax, [rbp+57h+var_70]
0x18002a1d3  mov     [rsp+0C0h+var_A0], rax; int
0x18002a1d8  call    ?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)
0x18002a1dd  mov     rcx, rdi; SRWLock
0x18002a1e0  mov     ebx, eax
0x18002a1e2  call    cs:__imp_ReleaseSRWLockShared
0x18002a1e8  test    ebx, ebx
0x18002a1ea  jns     short loc_18002A206
0x18002a1ec  mov     rcx, [rbp+5Fh]; this
0x18002a1f0  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18002a1f7  mov     r9d, ebx; char *
0x18002a1fa  mov     edx, 2DAh; void *
0x18002a1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a204  jmp     short loc_18002A208
0x18002a206  xor     ebx, ebx
0x18002a208  mov     rcx, r12; Block
0x18002a20b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a210  mov     eax, ebx
0x18002a212  mov     rcx, [rbp+57h+var_38]
0x18002a216  xor     rcx, rsp; StackCookie
0x18002a219  call    __security_check_cookie
0x18002a21e  add     rsp, 90h
0x18002a225  pop     r15
0x18002a227  pop     r14
0x18002a229  pop     r12
0x18002a22b  pop     rdi
0x18002a22c  pop     rsi
0x18002a22d  pop     rbx
0x18002a22e  pop     rbp
0x18002a22f  retn
```

# Apx::ApfIpcIoLinkMgr::RemoveCircuitDevice(unsigned __int64)

- ea: `0x180026c98`
- end: `0x180026e37`
- name: `?RemoveCircuitDevice@ApfIpcIoLinkMgr@Apx@@AEAAX_K@Z`
- size: `415`
- prototype: `void __fastcall(unsigned __int64 this, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180025b00`
- `0x180026e40`

## callees

- `0x180001d30`
- `0x18000a12c`
- `0x18000ba84`
- `0x180011e6c`
- `0x180026c98`
- `0x180027204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026de6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026de6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d05`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::RemoveCircuitDevice(unsigned __int64 this, __int64 a2)
{
  void *v4; // rcx
  int v5; // eax
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-38h] BYREF
  __int128 v7; // [rsp+58h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  NumberOfBytesTransferred = 0;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v4 = *(void **)(this + 88);
  if ( v4 )
  {
    *(_QWORD *)&v7 = a2;
    v5 = Apx::ApfHelper::SyncIoctl(v4, 0x1388u, 0x1DC004u, &v7, 0x10u, 0, 0, &NumberOfBytesTransferred, 0);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_qqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
        ~this,
        a2,
        v5);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qi(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids, ~this, a2);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180026c98  mov     [rsp+arg_10], rbx
0x180026c9d  push    rsi
0x180026c9e  push    rdi
0x180026c9f  push    r14
0x180026ca1  sub     rsp, 70h
0x180026ca5  mov     rax, cs:__security_cookie
0x180026cac  xor     rax, rsp
0x180026caf  mov     [rsp+88h+var_20], rax
0x180026cb4  mov     rsi, rdx
0x180026cb7  mov     rbx, rcx
0x180026cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cc1  lea     r14, WPP_GLOBAL_Control
0x180026cc8  cmp     rcx, r14
0x180026ccb  jz      short loc_180026CEE
0x180026ccd  test    byte ptr [rcx+1Ch], 1
0x180026cd1  jz      short loc_180026CEE
0x180026cd3  cmp     byte ptr [rcx+19h], 5
0x180026cd7  jb      short loc_180026CEE
0x180026cd9  mov     rcx, [rcx+10h]
0x180026cdd  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026ce4  mov     edx, 44h ; 'D'
0x180026ce9  call    WPP_SF_
0x180026cee  xorps   xmm0, xmm0
0x180026cf1  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x180026cf9  lea     rdi, [rbx+10h]
0x180026cfd  mov     rcx, rdi; lpCriticalSection
0x180026d00  movups  [rsp+88h+var_30], xmm0
0x180026d05  call    cs:__imp_EnterCriticalSection
0x180026d0b  mov     rcx, [rbx+58h]; void *
0x180026d0f  test    rcx, rcx
0x180026d12  jnz     short loc_180026D5D
0x180026d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d1b  cmp     rcx, r14
0x180026d1e  jz      loc_180026DE3
0x180026d24  test    byte ptr [rcx+1Ch], 80h
0x180026d28  jz      loc_180026DE3
0x180026d2e  cmp     byte ptr [rcx+19h], 4
0x180026d32  jb      loc_180026DE3
0x180026d38  mov     rcx, [rcx+10h]
0x180026d3c  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026d43  not     rbx
0x180026d46  mov     qword ptr [rsp+88h+nInBufferSize], rsi
0x180026d4b  mov     r9, rbx
0x180026d4e  mov     edx, 45h ; 'E'
0x180026d53  call    WPP_SF_qi
0x180026d58  jmp     loc_180026DE3
0x180026d5d  mov     [rsp+88h+var_48], 0; void *
0x180026d66  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x180026d6b  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180026d70  lea     r9, [rsp+88h+var_30]; void *
0x180026d75  mov     [rsp+88h+var_58], 0; DWORD
0x180026d7d  mov     edx, 1388h; unsigned int
0x180026d82  mov     [rsp+88h+var_60], 0; void *
0x180026d8b  mov     r8d, 1DC004h; unsigned int
0x180026d91  mov     [rsp+88h+nInBufferSize], 10h; nInBufferSize
0x180026d99  mov     qword ptr [rsp+88h+var_30], rsi
0x180026d9e  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x180026da3  test    eax, eax
0x180026da5  jns     short loc_180026DE3
0x180026da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dae  cmp     rcx, r14
0x180026db1  jz      short loc_180026DE3
0x180026db3  test    byte ptr [rcx+1Ch], 80h
0x180026db7  jz      short loc_180026DE3
0x180026db9  cmp     byte ptr [rcx+19h], 3
0x180026dbd  jb      short loc_180026DE3
0x180026dbf  mov     rcx, [rcx+10h]
0x180026dc3  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026dca  mov     dword ptr [rsp+88h+var_60], eax
0x180026dce  not     rbx
0x180026dd1  mov     r9, rbx
0x180026dd4  mov     qword ptr [rsp+88h+nInBufferSize], rsi
0x180026dd9  mov     edx, 46h ; 'F'
0x180026dde  call    WPP_SF_qqd
0x180026de3  mov     rcx, rdi; lpCriticalSection
0x180026de6  call    cs:__imp_LeaveCriticalSection
0x180026dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180026df3  cmp     rcx, r14
0x180026df6  jz      short loc_180026E19
0x180026df8  test    byte ptr [rcx+1Ch], 1
0x180026dfc  jz      short loc_180026E19
0x180026dfe  cmp     byte ptr [rcx+19h], 5
0x180026e02  jb      short loc_180026E19
0x180026e04  mov     rcx, [rcx+10h]
0x180026e08  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026e0f  mov     edx, 47h ; 'G'
0x180026e14  call    WPP_SF_
0x180026e19  mov     rcx, [rsp+88h+var_20]
0x180026e1e  xor     rcx, rsp; StackCookie
0x180026e21  call    __security_check_cookie
0x180026e26  mov     rbx, [rsp+88h+arg_10]
0x180026e2e  add     rsp, 70h
0x180026e32  pop     r14
0x180026e34  pop     rdi
0x180026e35  pop     rsi
0x180026e36  retn
```

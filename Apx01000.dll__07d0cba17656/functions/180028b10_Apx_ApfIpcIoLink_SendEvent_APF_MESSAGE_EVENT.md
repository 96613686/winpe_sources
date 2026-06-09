# Apx::ApfIpcIoLink::SendEvent(APF_MESSAGE_EVENT *)

- ea: `0x180028b10`
- end: `0x180028d77`
- name: `?SendEvent@ApfIpcIoLink@Apx@@UEAAXPEAUAPF_MESSAGE_EVENT@@@Z`
- size: `615`
- prototype: `void __fastcall(unsigned __int64 this, struct APF_MESSAGE_EVENT *Src)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x18000213c`
- `0x18000a12c`
- `0x18000c7ec`
- `0x180011e6c`
- `0x180027754`
- `0x18002812c`
- `0x180028b10`
- `0x180029118`
- `0x1800292ec`
- `0x180029880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028cd6`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::SendEvent(unsigned __int64 this, struct APF_MESSAGE_EVENT *Src)
{
  unsigned __int64 v4; // rax
  _QWORD *v5; // rax
  char *v6; // rdi
  _QWORD *v7; // rcx
  _QWORD *v8; // rsi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  Apx::ApfIpcIoLink **v12; // rcx
  int v13; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  v4 = 8 * (((unsigned __int64)(unsigned int)(*(_DWORD *)Src + *((_DWORD *)Src + 7)) + 16) >> 3);
  if ( !is_mul_ok(((unsigned __int64)(unsigned int)(*(_DWORD *)Src + *((_DWORD *)Src + 7)) + 16) >> 3, 8u) )
    v4 = -1;
  v5 = operator new[](v4, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (char *)v5;
  if ( v5 )
  {
    v5[1] = v5;
    v8 = v5 + 2;
    *v5 = v5;
    memcpy_0(v5 + 2, Src, (unsigned int)(*(_DWORD *)Src + *((_DWORD *)Src + 7)));
    *((_QWORD *)v6 + 3) = *(_QWORD *)(this + 64);
    if ( (*((_BYTE *)v8 + 4) & 0x10) != 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v10 = 61;
LABEL_21:
        WPP_SF_iqidD(
          v9[2],
          v10,
          *((unsigned __int16 *)v8 + 12),
          *(_QWORD *)(this + 64),
          v8,
          v8[2],
          *((unsigned __int16 *)v8 + 12),
          *((unsigned __int16 *)v8 + 13));
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v10 = 62;
        goto LABEL_21;
      }
    }
    if ( Apx::ApfIpcIoLink::StartOperation((Apx::ApfIpcIoLink *)this) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
      v12 = *(Apx::ApfIpcIoLink ***)(this + 408);
      if ( *v12 != (Apx::ApfIpcIoLink *)(this + 400) )
        __fastfail(3u);
      *((_QWORD *)v6 + 1) = v12;
      *(_QWORD *)v6 = this + 400;
      *v12 = (Apx::ApfIpcIoLink *)v6;
      *(_QWORD *)(this + 408) = v6;
      v13 = Apx::ApfWorkItemQueue::AddWorkItemToQueue(
              (Apx::ApfWorkItemQueue *)(this + 264),
              (struct Apx::ApfWorkItemBase *)(this + 384));
      if ( v13 < 0 )
        Apx::ApfIpcIoLink::ApfLogEventResult(
          (Apx::ApfIpcIoLink *)this,
          (struct APF_MESSAGE_EVENT *)v8,
          v13,
          "event not sent, queue is in rundown state");
      LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
      Apx::ApfIpcIoLink::EndOperation((Apx::ApfIpcIoLink *)this);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
          ~this,
          *(_QWORD *)(this + 64),
          -2147467260);
      }
      Apx::ApfIpcIoLink::ApfLogEventResult(
        (Apx::ApfIpcIoLink *)this,
        (struct APF_MESSAGE_EVENT *)(v6 + 16),
        -2147467260,
        "event not sent, queue is in rundown state");
      operator delete(v6, v11);
    }
    goto LABEL_33;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
LABEL_33:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_(v7[2], 44, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
}

```

## disassembly

```asm
0x180028b10  push    rbx
0x180028b12  push    rbp
0x180028b13  push    rsi
0x180028b14  push    rdi
0x180028b15  push    r14
0x180028b17  sub     rsp, 40h
0x180028b1b  mov     rbp, rdx
0x180028b1e  mov     rbx, rcx
0x180028b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b28  lea     r14, WPP_GLOBAL_Control
0x180028b2f  cmp     rcx, r14
0x180028b32  jz      short loc_180028B55
0x180028b34  test    byte ptr [rcx+1Ch], 1
0x180028b38  jz      short loc_180028B55
0x180028b3a  cmp     byte ptr [rcx+19h], 5
0x180028b3e  jb      short loc_180028B55
0x180028b40  mov     rcx, [rcx+10h]
0x180028b44  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028b4b  mov     edx, 29h ; ')'
0x180028b50  call    WPP_SF_
0x180028b55  mov     ecx, [rbp+1Ch]
0x180028b58  mov     eax, 8
0x180028b5d  add     ecx, [rbp+0]
0x180028b60  add     rcx, 10h
0x180028b64  shr     rcx, 3
0x180028b68  mul     rcx
0x180028b6b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180028b72  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028b79  cmovb   rax, rcx
0x180028b7d  mov     rcx, rax; unsigned __int64
0x180028b80  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028b85  mov     rdi, rax
0x180028b88  test    rax, rax
0x180028b8b  jnz     short loc_180028BC9
0x180028b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b94  cmp     rcx, r14
0x180028b97  jz      loc_180028D6C
0x180028b9d  test    byte ptr [rcx+1Ch], 20h
0x180028ba1  jz      loc_180028D46
0x180028ba7  cmp     byte ptr [rcx+19h], 2
0x180028bab  jb      loc_180028D46
0x180028bb1  mov     rcx, [rcx+10h]
0x180028bb5  lea     edx, [rax+2Ah]
0x180028bb8  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028bbf  call    WPP_SF_
0x180028bc4  jmp     loc_180028D3F
0x180028bc9  mov     [rax+8], rdi
0x180028bcd  lea     rsi, [rax+10h]
0x180028bd1  mov     [rax], rdi
0x180028bd4  mov     rdx, rbp; Src
0x180028bd7  mov     r8d, [rbp+1Ch]
0x180028bdb  mov     rcx, rsi; void *
0x180028bde  add     r8d, [rbp+0]; Size
0x180028be2  call    memcpy_0
0x180028be7  mov     rax, [rbx+40h]
0x180028beb  mov     bpl, 80h
0x180028bee  mov     [rdi+18h], rax
0x180028bf2  test    byte ptr [rsi+4], 10h
0x180028bf6  jz      short loc_180028C17
0x180028bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bff  cmp     rcx, r14
0x180028c02  jz      short loc_180028C61
0x180028c04  test    [rcx+1Ch], bpl
0x180028c08  jz      short loc_180028C61
0x180028c0a  cmp     byte ptr [rcx+19h], 5
0x180028c0e  jb      short loc_180028C61
0x180028c10  mov     edx, 3Dh ; '='
0x180028c15  jmp     short loc_180028C34
0x180028c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c1e  cmp     rcx, r14
0x180028c21  jz      short loc_180028C61
0x180028c23  test    [rcx+1Ch], bpl
0x180028c27  jz      short loc_180028C61
0x180028c29  cmp     byte ptr [rcx+19h], 4
0x180028c2d  jb      short loc_180028C61
0x180028c2f  mov     edx, 3Eh ; '>'
0x180028c34  movzx   eax, word ptr [rsi+1Ah]
0x180028c38  movzx   r8d, word ptr [rsi+18h]
0x180028c3d  mov     r9, [rbx+40h]
0x180028c41  mov     rcx, [rcx+10h]
0x180028c45  mov     [rsp+68h+var_30], eax
0x180028c49  mov     rax, [rsi+10h]
0x180028c4d  mov     [rsp+68h+var_38], r8d
0x180028c52  mov     [rsp+68h+var_40], rax
0x180028c57  mov     [rsp+68h+var_48], rsi
0x180028c5c  call    WPP_SF_iqidD
0x180028c61  mov     rcx, rbx; this
0x180028c64  call    ?StartOperation@ApfIpcIoLink@Apx@@AEAA_NXZ; Apx::ApfIpcIoLink::StartOperation(void)
0x180028c69  test    al, al
0x180028c6b  jnz     short loc_180028CD2
0x180028c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c74  mov     esi, 80004004h
0x180028c79  cmp     rcx, r14
0x180028c7c  jz      short loc_180028CB2
0x180028c7e  test    [rcx+1Ch], bpl
0x180028c82  jz      short loc_180028CB2
0x180028c84  cmp     byte ptr [rcx+19h], 4
0x180028c88  jb      short loc_180028CB2
0x180028c8a  mov     rax, [rbx+40h]
0x180028c8e  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028c95  mov     rcx, [rcx+10h]
0x180028c99  mov     r9, rbx
0x180028c9c  not     r9
0x180028c9f  mov     dword ptr [rsp+68h+var_40], esi
0x180028ca3  mov     edx, 2Bh ; '+'
0x180028ca8  mov     [rsp+68h+var_48], rax
0x180028cad  call    WPP_SF_qqd
0x180028cb2  lea     rdx, [rdi+10h]; struct APF_MESSAGE_EVENT *
0x180028cb6  mov     r8d, esi; int
0x180028cb9  lea     r9, aEventNotSentQu; "event not sent, queue is in rundown sta"...
0x180028cc0  mov     rcx, rbx; this
0x180028cc3  call    ?ApfLogEventResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_EVENT@@JPEBD@Z; Apx::ApfIpcIoLink::ApfLogEventResult(APF_MESSAGE_EVENT *,long,char const *)
0x180028cc8  mov     rcx, rdi; void *
0x180028ccb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028cd0  jmp     short loc_180028D3F
0x180028cd2  lea     rcx, [rbx+10h]; lpCriticalSection
0x180028cd6  call    cs:__imp_EnterCriticalSection
0x180028cdc  lea     rax, [rbx+190h]
0x180028ce3  mov     rcx, [rax+8]
0x180028ce7  cmp     [rcx], rax
0x180028cea  jz      short loc_180028CF3
0x180028cec  mov     ecx, 3
0x180028cf1  int     29h; Win8: RtlFailFast(ecx)
0x180028cf3  mov     [rdi+8], rcx
0x180028cf7  lea     rdx, [rbx+180h]; struct Apx::ApfWorkItemBase *
0x180028cfe  mov     [rdi], rax
0x180028d01  mov     [rcx], rdi
0x180028d04  lea     rcx, [rbx+108h]; this
0x180028d0b  mov     [rax+8], rdi
0x180028d0f  call    ?AddWorkItemToQueue@ApfWorkItemQueue@Apx@@QEAAJPEAVApfWorkItemBase@2@@Z; Apx::ApfWorkItemQueue::AddWorkItemToQueue(Apx::ApfWorkItemBase *)
0x180028d14  test    eax, eax
0x180028d16  jns     short loc_180028D2D
0x180028d18  lea     r9, aEventNotSentQu; "event not sent, queue is in rundown sta"...
0x180028d1f  mov     r8d, eax; int
0x180028d22  mov     rdx, rsi; struct APF_MESSAGE_EVENT *
0x180028d25  mov     rcx, rbx; this
0x180028d28  call    ?ApfLogEventResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_EVENT@@JPEBD@Z; Apx::ApfIpcIoLink::ApfLogEventResult(APF_MESSAGE_EVENT *,long,char const *)
0x180028d2d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180028d31  call    cs:__imp_LeaveCriticalSection
0x180028d37  mov     rcx, rbx; this
0x180028d3a  call    ?EndOperation@ApfIpcIoLink@Apx@@AEAAXXZ; Apx::ApfIpcIoLink::EndOperation(void)
0x180028d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d46  cmp     rcx, r14
0x180028d49  jz      short loc_180028D6C
0x180028d4b  test    byte ptr [rcx+1Ch], 1
0x180028d4f  jz      short loc_180028D6C
0x180028d51  cmp     byte ptr [rcx+19h], 5
0x180028d55  jb      short loc_180028D6C
0x180028d57  mov     rcx, [rcx+10h]
0x180028d5b  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028d62  mov     edx, 2Ch ; ','
0x180028d67  call    WPP_SF_
0x180028d6c  add     rsp, 40h
0x180028d70  pop     r14
0x180028d72  pop     rdi
0x180028d73  pop     rsi
0x180028d74  pop     rbp
0x180028d75  pop     rbx
0x180028d76  retn
```

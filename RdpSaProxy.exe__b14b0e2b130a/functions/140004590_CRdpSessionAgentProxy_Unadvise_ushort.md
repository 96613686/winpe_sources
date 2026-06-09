# CRdpSessionAgentProxy::Unadvise(ushort *)

- ea: `0x140004590`
- end: `0x140004743`
- name: `?Unadvise@CRdpSessionAgentProxy@@UEAAJPEAG@Z`
- size: `435`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140004590`
- `0x1400056c9`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x14000463c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000463c`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::Unadvise(CRdpSessionAgentProxy *this, unsigned __int16 *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx

  if ( !*((_QWORD *)this + 11) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147483658LL;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 36;
LABEL_30:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147483638);
    return 2147483658LL;
  }
  if ( a2 )
  {
    if ( SysStringByteLen(a2) == 64 )
    {
      if ( !memcmp_0(a2, *((const void **)this + 11), 0x40u) )
      {
        if ( !*((_QWORD *)this + 7) )
          return 0;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 2147483658LL;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 40;
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147942405LL;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 39;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147942405LL;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 38;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v8, -2147024891);
    return 2147942405LL;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v6, -2147467261);
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x140004590  mov     [rsp+arg_0], rbx
0x140004595  push    rdi
0x140004596  sub     rsp, 30h
0x14000459a  cmp     qword ptr [rcx+58h], 0
0x14000459f  mov     rdi, rdx
0x1400045a2  mov     rbx, rcx
0x1400045a5  jnz     short loc_1400045E1
0x1400045a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045ae  lea     rax, WPP_GLOBAL_Control
0x1400045b5  cmp     rcx, rax
0x1400045b8  jz      loc_140004733
0x1400045be  test    byte ptr [rcx+1Ch], 8
0x1400045c2  jz      loc_140004733
0x1400045c8  cmp     byte ptr [rcx+19h], 2
0x1400045cc  jb      loc_140004733
0x1400045d2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400045d7  mov     edx, 24h ; '$'
0x1400045dc  jmp     loc_140004711
0x1400045e1  test    rdi, rdi
0x1400045e4  jnz     short loc_140004639
0x1400045e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045ed  lea     rax, WPP_GLOBAL_Control
0x1400045f4  cmp     rcx, rax
0x1400045f7  jz      short loc_14000462F
0x1400045f9  test    byte ptr [rcx+1Ch], 8
0x1400045fd  jz      short loc_14000462F
0x1400045ff  cmp     byte ptr [rcx+19h], 2
0x140004603  jb      short loc_14000462F
0x140004605  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000460a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004611  lea     edx, [rdi+25h]
0x140004614  mov     r9d, eax
0x140004617  mov     [rsp+38h+var_18], 80004003h
0x14000461f  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004626  mov     rcx, [rcx+10h]
0x14000462a  call    WPP_SF_Dd
0x14000462f  mov     eax, 80004003h
0x140004634  jmp     loc_140004738
0x140004639  mov     rcx, rdi; bstr
0x14000463c  call    cs:__imp_SysStringByteLen
0x140004642  mov     r8d, 40h ; '@'; Size
0x140004648  cmp     eax, r8d
0x14000464b  jz      short loc_1400046A2
0x14000464d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004654  lea     rax, WPP_GLOBAL_Control
0x14000465b  cmp     rcx, rax
0x14000465e  jz      short loc_140004698
0x140004660  test    byte ptr [rcx+1Ch], 8
0x140004664  jz      short loc_140004698
0x140004666  cmp     byte ptr [rcx+19h], 2
0x14000466a  jb      short loc_140004698
0x14000466c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004671  mov     edx, 26h ; '&'
0x140004676  mov     rcx, cs:WPP_GLOBAL_Control
0x14000467d  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004684  mov     r9d, eax
0x140004687  mov     [rsp+38h+var_18], 80070005h
0x14000468f  mov     rcx, [rcx+10h]
0x140004693  call    WPP_SF_Dd
0x140004698  mov     eax, 80070005h
0x14000469d  jmp     loc_140004738
0x1400046a2  mov     rdx, [rbx+58h]; Buf2
0x1400046a6  mov     rcx, rdi; Buf1
0x1400046a9  call    memcmp_0
0x1400046ae  test    eax, eax
0x1400046b0  jz      short loc_1400046DD
0x1400046b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046b9  lea     rax, WPP_GLOBAL_Control
0x1400046c0  cmp     rcx, rax
0x1400046c3  jz      short loc_140004698
0x1400046c5  test    byte ptr [rcx+1Ch], 8
0x1400046c9  jz      short loc_140004698
0x1400046cb  cmp     byte ptr [rcx+19h], 2
0x1400046cf  jb      short loc_140004698
0x1400046d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400046d6  mov     edx, 27h ; '''
0x1400046db  jmp     short loc_140004676
0x1400046dd  cmp     qword ptr [rbx+38h], 0
0x1400046e2  jnz     short loc_1400046E8
0x1400046e4  xor     eax, eax
0x1400046e6  jmp     short loc_140004738
0x1400046e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ef  lea     rax, WPP_GLOBAL_Control
0x1400046f6  cmp     rcx, rax
0x1400046f9  jz      short loc_140004733
0x1400046fb  test    byte ptr [rcx+1Ch], 8
0x1400046ff  jz      short loc_140004733
0x140004701  cmp     byte ptr [rcx+19h], 2
0x140004705  jb      short loc_140004733
0x140004707  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000470c  mov     edx, 28h ; '('
0x140004711  mov     rcx, cs:WPP_GLOBAL_Control
0x140004718  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x14000471f  mov     r9d, eax
0x140004722  mov     [rsp+38h+var_18], 8000000Ah
0x14000472a  mov     rcx, [rcx+10h]
0x14000472e  call    WPP_SF_Dd
0x140004733  mov     eax, 8000000Ah
0x140004738  mov     rbx, [rsp+38h+arg_0]
0x14000473d  add     rsp, 30h
0x140004741  pop     rdi
0x140004742  retn
```

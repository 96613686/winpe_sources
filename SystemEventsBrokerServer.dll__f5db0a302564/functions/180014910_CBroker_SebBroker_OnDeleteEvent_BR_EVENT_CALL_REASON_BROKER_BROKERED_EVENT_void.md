# CBroker::SebBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x180014910`
- end: `0x180014a6d`
- name: `?OnDeleteEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `349`
- prototype: `static unsigned int __high(enum _BR_EVENT_CALL_REASON, struct _BROKER *, struct _BROKERED_EVENT *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x180014910`
- `0x18001a99c`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall CBroker::SebBroker::OnDeleteEvent(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  unsigned int v7; // edi

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  if ( a2 && a3 && a4 )
  {
    if ( (byte_180035F64[40 * a4[24] - 163840] & 1) != 0
      && (unsigned int)CBroker::SebEvent::DecRefCount((CBroker::SebEvent *)a4) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
      v7 = 0;
    }
    else
    {
      v7 = 0;
      (**(void (__fastcall ***)(int *, __int64))a4)(a4, 1);
    }
  }
  else
  {
    v7 = 87;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180014910  mov     [rsp+arg_0], rbx
0x180014915  mov     [rsp+arg_10], rsi
0x18001491a  push    rdi
0x18001491b  sub     rsp, 40h
0x18001491f  mov     rbx, r9
0x180014922  mov     rdi, r8
0x180014925  mov     rsi, rdx
0x180014928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001492f  test    byte ptr [rcx+1Ch], 8
0x180014933  jnz     short loc_1800149A4
0x180014935  test    rsi, rsi
0x180014938  jz      loc_180014A3C
0x18001493e  test    rdi, rdi
0x180014941  jz      loc_180014A3C
0x180014947  test    rbx, rbx
0x18001494a  jz      loc_180014A3C
0x180014950  movsxd  rax, dword ptr [rbx+60h]
0x180014954  sub     rax, 1000h
0x18001495a  lea     rax, [rax+rax*4]
0x18001495e  lea     rcx, byte_180035F64
0x180014965  test    byte ptr [rcx+rax*8], 1
0x180014969  jnz     short loc_1800149C4
0x18001496b  xor     edi, edi
0x18001496d  mov     rax, [rbx]
0x180014970  mov     edx, 1
0x180014975  mov     rcx, rbx
0x180014978  mov     rax, [rax]
0x18001497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014980  nop
0x180014981  mov     rcx, cs:WPP_GLOBAL_Control
0x180014988  test    byte ptr [rcx+1Ch], 8
0x18001498c  jnz     loc_180014A46
0x180014992  mov     eax, edi
0x180014994  mov     rbx, [rsp+48h+arg_0]
0x180014999  mov     rsi, [rsp+48h+arg_10]
0x18001499e  add     rsp, 40h
0x1800149a2  pop     rdi
0x1800149a3  retn
0x1800149a4  cmp     byte ptr [rcx+19h], 4
0x1800149a8  jb      short loc_180014935
0x1800149aa  mov     edx, 32h ; '2'
0x1800149af  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800149b6  mov     rcx, [rcx+10h]
0x1800149ba  call    WPP_SF_
0x1800149bf  jmp     loc_180014935
0x1800149c4  mov     rcx, rbx; this
0x1800149c7  call    ?DecRefCount@SebEvent@CBroker@@QEAAHXZ; CBroker::SebEvent::DecRefCount(void)
0x1800149cc  cmp     eax, 1
0x1800149cf  jb      short loc_18001496B
0x1800149d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149d8  test    byte ptr [rcx+1Ch], 8
0x1800149dc  jz      short loc_1800149F9
0x1800149de  cmp     byte ptr [rcx+19h], 4
0x1800149e2  jb      short loc_1800149F9
0x1800149e4  mov     edx, 33h ; '3'
0x1800149e9  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800149f0  mov     rcx, [rcx+10h]
0x1800149f4  call    WPP_SF_
0x1800149f9  xor     edi, edi
0x1800149fb  jmp     short loc_180014981
0x1800149fd  mov     edi, [rsp+48h+arg_8]
0x180014a01  jmp     loc_180014981
0x180014a06  mov     edi, [rsp+48h+arg_8]
0x180014a0a  jmp     loc_180014981
0x180014a0f  mov     edi, [rsp+48h+arg_8]
0x180014a13  jmp     loc_180014981
0x180014a18  mov     edi, [rsp+48h+arg_8]
0x180014a1c  jmp     loc_180014981
0x180014a21  mov     edi, [rsp+48h+arg_8]
0x180014a25  jmp     loc_180014981
0x180014a2a  mov     edi, [rsp+48h+arg_8]
0x180014a2e  jmp     loc_180014981
0x180014a33  mov     edi, [rsp+48h+arg_8]
0x180014a37  jmp     loc_180014981
0x180014a3c  mov     edi, 57h ; 'W'
0x180014a41  jmp     loc_180014981
0x180014a46  cmp     byte ptr [rcx+19h], 4
0x180014a4a  jb      loc_180014992
0x180014a50  mov     edx, 36h ; '6'
0x180014a55  mov     r9d, edi
0x180014a58  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x180014a5f  mov     rcx, [rcx+10h]
0x180014a63  call    WPP_SF_d
0x180014a68  jmp     loc_180014992
```

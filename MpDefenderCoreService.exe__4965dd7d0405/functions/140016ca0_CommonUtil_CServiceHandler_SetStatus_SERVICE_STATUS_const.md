# CommonUtil::CServiceHandler::SetStatus(_SERVICE_STATUS const &)

- ea: `0x140016ca0`
- end: `0x140016d9f`
- name: `?SetStatus@CServiceHandler@CommonUtil@@UEAAXAEBU_SERVICE_STATUS@@@Z`
- size: `255`
- prototype: `void __fastcall(CommonUtil::CServiceHandler *__hidden this, const struct _SERVICE_STATUS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140016ca0`
- `0x140016f84`
- `0x140017738`
- `0x140085eb4`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x140016d51`
- `ADVAPI32!SetServiceStatus` at `0x140016d51`

## pseudocode

```c
void __fastcall CommonUtil::CServiceHandler::SetStatus(
        CommonUtil::CServiceHandler *this,
        const struct _SERVICE_STATUS *a2)
{
  struct _SERVICE_STATUS *v2; // rdi
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int LastFailure; // eax

  v2 = (struct _SERVICE_STATUS *)((char *)this + 64);
  *(struct _SERVICE_STATUS *)((char *)this + 64) = *a2;
  v4 = *((_DWORD *)this + 17);
  *((_DWORD *)this + 21) = 0;
  *((_DWORD *)this + 16) = 16;
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 && (v7 = v6 - 1) != 0 )
    {
      if ( v7 == 1 )
        *((_BYTE *)this + 108) = 1;
    }
    else
    {
      *((_DWORD *)this + 21) = ++*((_DWORD *)this + 26);
    }
  }
  else
  {
    *((_BYTE *)this + 108) = 0;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_LLLL(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids);
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 12), v2) )
  {
    LastFailure = HrGetLastFailure();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        42,
        WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        *((unsigned int *)this + 17),
        LastFailure);
  }
}

```

## disassembly

```asm
0x140016ca0  mov     [rsp+arg_0], rbx
0x140016ca5  mov     [rsp+arg_8], rsi
0x140016caa  push    rdi
0x140016cab  sub     rsp, 40h
0x140016caf  movups  xmm0, xmmword ptr [rdx]
0x140016cb2  lea     rdi, [rcx+40h]
0x140016cb6  mov     rbx, rcx
0x140016cb9  movups  xmmword ptr [rdi], xmm0
0x140016cbc  movsd   xmm1, qword ptr [rdx+10h]
0x140016cc1  movsd   qword ptr [rdi+10h], xmm1
0x140016cc6  mov     eax, [rdx+18h]
0x140016cc9  mov     [rdi+18h], eax
0x140016ccc  mov     r9d, [rcx+44h]
0x140016cd0  mov     eax, r9d
0x140016cd3  mov     dword ptr [rcx+54h], 0
0x140016cda  xor     ecx, ecx
0x140016cdc  mov     dword ptr [rdi], 10h
0x140016ce2  sub     eax, 1
0x140016ce5  jz      short loc_140016D06
0x140016ce7  sub     eax, 1
0x140016cea  jz      short loc_140016CFB
0x140016cec  sub     eax, 1
0x140016cef  jz      short loc_140016CFB
0x140016cf1  cmp     eax, 1
0x140016cf4  jnz     short loc_140016D09
0x140016cf6  mov     [rbx+6Ch], al
0x140016cf9  jmp     short loc_140016D09
0x140016cfb  inc     dword ptr [rbx+68h]
0x140016cfe  mov     ecx, [rbx+68h]
0x140016d01  mov     [rbx+54h], ecx
0x140016d04  jmp     short loc_140016D09
0x140016d06  mov     [rbx+6Ch], cl
0x140016d09  mov     r10, cs:WPP_GLOBAL_Control
0x140016d10  lea     rsi, WPP_GLOBAL_Control
0x140016d17  cmp     r10, rsi
0x140016d1a  jz      short loc_140016D4A
0x140016d1c  test    byte ptr [r10+1Ch], 4
0x140016d21  jz      short loc_140016D4A
0x140016d23  mov     eax, [rbx+58h]
0x140016d26  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016d2d  mov     [rsp+48h+var_18], eax
0x140016d31  mov     edx, 29h ; ')'
0x140016d36  mov     eax, [rbx+48h]
0x140016d39  mov     [rsp+48h+var_20], ecx
0x140016d3d  mov     rcx, [r10+10h]
0x140016d41  mov     [rsp+48h+var_28], eax
0x140016d45  call    WPP_SF_LLLL
0x140016d4a  mov     rcx, [rbx+60h]; hServiceStatus
0x140016d4e  mov     rdx, rdi; lpServiceStatus
0x140016d51  call    cs:__imp_SetServiceStatus
0x140016d57  test    eax, eax
0x140016d59  jnz     short loc_140016D8F
0x140016d5b  call    HrGetLastFailure
0x140016d60  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d67  cmp     rcx, rsi
0x140016d6a  jz      short loc_140016D8F
0x140016d6c  test    byte ptr [rcx+1Ch], 1
0x140016d70  jz      short loc_140016D8F
0x140016d72  mov     r9d, [rbx+44h]
0x140016d76  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016d7d  mov     rcx, [rcx+10h]
0x140016d81  mov     edx, 2Ah ; '*'
0x140016d86  mov     [rsp+48h+var_28], eax
0x140016d8a  call    WPP_SF_Dd
0x140016d8f  mov     rbx, [rsp+48h+arg_0]
0x140016d94  mov     rsi, [rsp+48h+arg_8]
0x140016d99  add     rsp, 40h
0x140016d9d  pop     rdi
0x140016d9e  retn
```

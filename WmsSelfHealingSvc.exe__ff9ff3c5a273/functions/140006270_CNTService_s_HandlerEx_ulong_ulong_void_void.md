# CNTService::s_HandlerEx(ulong,ulong,void *,void *)

- ea: `0x140006270`
- end: `0x1400063d9`
- name: `?s_HandlerEx@CNTService@@SAKKKPEAX0@Z`
- size: `361`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x1400036a0`
- `0x1400058e8`
- `0x140006270`
- `0x14000ae26`
- `0x14000c010`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x140006395`
- `ADVAPI32!SetServiceStatus` at `0x140006395`

## string_xrefs

- `0x140006378`: `CNTService::s_HandlerEx ::SetServiceStatus (0x%IX, %lu)\n`

## pseudocode

```c
__int64 __fastcall CNTService::s_HandlerEx(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  CNTService *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  struct _SERVICE_STATUS *v8; // rdi
  __int128 v9; // xmm1

  v4 = CNTService::s_pSingleInstance;
  if ( dwControl == 1 )
  {
    CNTService::SetStatus(CNTService::s_pSingleInstance, 3u);
    (*(void (__fastcall **)(CNTService *))(*(_QWORD *)v4 + 40LL))(v4);
  }
  else
  {
    switch ( dwControl )
    {
      case 2u:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 56LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 3u:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 64LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 4u:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 48LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 5u:
        CNTService::SetStatus(CNTService::s_pSingleInstance, 3u);
        (*(void (__fastcall **)(CNTService *, __int64, __int64, __int64))(*(_QWORD *)v4 + 72LL))(v4, v5, v6, v7);
        break;
      case 0xBu:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 88LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 0xDu:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 104LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 0xEu:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 96LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      case 0x10u:
        (*(void (__fastcall **)(CNTService *, __int64, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 112LL))(
          CNTService::s_pSingleInstance,
          dwEventType,
          lpEventData,
          lpContext);
        break;
      default:
        if ( dwControl >= 0x80 )
          (*(void (__fastcall **)(CNTService *, _QWORD, LPVOID, LPVOID))(*(_QWORD *)CNTService::s_pSingleInstance + 120LL))(
            CNTService::s_pSingleInstance,
            dwControl,
            lpEventData,
            lpContext);
        break;
    }
    v8 = (struct _SERVICE_STATUS *)((char *)v4 + 784);
    if ( memcmp_0((char *)v4 + 784, (char *)v4 + 812, 0x1Cu) )
    {
      DEBUGMSG(
        L"CNTService::s_HandlerEx ::SetServiceStatus (0x%IX, %lu)\n",
        *((_QWORD *)v4 + 97),
        *((unsigned int *)v4 + 197));
      SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v4 + 97), v8);
      v9 = *(_OWORD *)((char *)v4 + 796);
      *(_OWORD *)((char *)v4 + 812) = *(_OWORD *)&v8->dwServiceType;
      *(_OWORD *)((char *)v4 + 824) = v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140006270  mov     [rsp+arg_0], rbx
0x140006275  mov     [rsp+arg_8], rsi
0x14000627a  push    rdi
0x14000627b  sub     rsp, 20h
0x14000627f  mov     rbx, cs:?s_pSingleInstance@CNTService@@2PEAV1@EA; CNTService * CNTService::s_pSingleInstance
0x140006286  mov     eax, ecx
0x140006288  sub     eax, 1
0x14000628b  jz      loc_1400063AB
0x140006291  sub     eax, 1
0x140006294  jz      loc_14000633F
0x14000629a  sub     eax, 1
0x14000629d  jz      loc_140006336
0x1400062a3  sub     eax, 1
0x1400062a6  jz      loc_14000632D
0x1400062ac  sub     eax, 1
0x1400062af  jz      short loc_140006317
0x1400062b1  sub     eax, 6
0x1400062b4  jz      short loc_14000630E
0x1400062b6  sub     eax, 2
0x1400062b9  jz      short loc_140006305
0x1400062bb  sub     eax, 1
0x1400062be  jz      short loc_1400062F4
0x1400062c0  cmp     eax, 2
0x1400062c3  jz      short loc_1400062EB
0x1400062c5  cmp     ecx, 80h
0x1400062cb  jb      short loc_1400062E0
0x1400062cd  mov     rax, [rbx]
0x1400062d0  mov     edx, ecx
0x1400062d2  mov     rcx, rbx
0x1400062d5  mov     rax, [rax+78h]
0x1400062d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062de  jmp     short loc_14000634E
0x1400062e0  cmp     ecx, 1
0x1400062e3  jz      loc_1400063C7
0x1400062e9  jmp     short loc_14000634E
0x1400062eb  mov     rax, [rbx]
0x1400062ee  mov     rax, [rax+70h]
0x1400062f2  jmp     short loc_140006346
0x1400062f4  mov     rax, [rbx]
0x1400062f7  mov     rax, [rax+60h]
0x1400062fb  mov     rcx, rbx
0x1400062fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006303  jmp     short loc_14000634E
0x140006305  mov     rax, [rbx]
0x140006308  mov     rax, [rax+68h]
0x14000630c  jmp     short loc_1400062FB
0x14000630e  mov     rax, [rbx]
0x140006311  mov     rax, [rax+58h]
0x140006315  jmp     short loc_1400062FB
0x140006317  mov     edx, 3; unsigned int
0x14000631c  mov     rcx, rbx; this
0x14000631f  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x140006324  mov     rax, [rbx]
0x140006327  mov     rax, [rax+48h]
0x14000632b  jmp     short loc_140006346
0x14000632d  mov     rax, [rbx]
0x140006330  mov     rax, [rax+30h]
0x140006334  jmp     short loc_140006346
0x140006336  mov     rax, [rbx]
0x140006339  mov     rax, [rax+40h]
0x14000633d  jmp     short loc_140006346
0x14000633f  mov     rax, [rbx]
0x140006342  mov     rax, [rax+38h]
0x140006346  mov     rcx, rbx
0x140006349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000634e  lea     rdi, [rbx+310h]
0x140006355  mov     r8d, 1Ch; Size
0x14000635b  lea     rsi, [rbx+32Ch]
0x140006362  mov     rcx, rdi; Buf1
0x140006365  mov     rdx, rsi; Buf2
0x140006368  call    memcmp_0
0x14000636d  test    eax, eax
0x14000636f  jz      short loc_1400063C7
0x140006371  mov     r8d, [rbx+314h]
0x140006378  lea     rcx, aCntserviceSHan; "CNTService::s_HandlerEx ::SetServiceSta"...
0x14000637f  mov     rdx, [rbx+308h]
0x140006386  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000638b  mov     rcx, [rbx+308h]; hServiceStatus
0x140006392  mov     rdx, rdi; lpServiceStatus
0x140006395  call    cs:__imp_SetServiceStatus
0x14000639b  movups  xmm0, xmmword ptr [rdi]
0x14000639e  movups  xmm1, xmmword ptr [rdi+0Ch]
0x1400063a2  movups  xmmword ptr [rsi], xmm0
0x1400063a5  movups  xmmword ptr [rsi+0Ch], xmm1
0x1400063a9  jmp     short loc_1400063C7
0x1400063ab  mov     edx, 3; unsigned int
0x1400063b0  mov     rcx, rbx; this
0x1400063b3  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x1400063b8  mov     rax, [rbx]
0x1400063bb  mov     rcx, rbx
0x1400063be  mov     rax, [rax+28h]
0x1400063c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063c7  mov     rbx, [rsp+28h+arg_0]
0x1400063cc  xor     eax, eax
0x1400063ce  mov     rsi, [rsp+28h+arg_8]
0x1400063d3  add     rsp, 20h
0x1400063d7  pop     rdi
0x1400063d8  retn
```

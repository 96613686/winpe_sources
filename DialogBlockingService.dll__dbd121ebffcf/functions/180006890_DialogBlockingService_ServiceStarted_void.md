# DialogBlockingService::ServiceStarted(void)

- ea: `0x180006890`
- end: `0x180006960`
- name: `?ServiceStarted@DialogBlockingService@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(DialogBlockingService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180004140`

## callees

- `0x180001644`
- `0x180001650`
- `0x1800020d0`
- `0x180006890`
- `0x1800099d8`

## pseudocode

```c
__int64 __fastcall DialogBlockingService::ServiceStarted(DialogBlockingService *this)
{
  _QWORD *v2; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  Windows::Internal::DialogBlocking::ServiceSessions *v5; // rdi
  __int64 result; // rax
  __int64 v7; // [rsp+0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v9; // [rsp+38h] [rbp+10h]

  try
  {
    v9 = (char *)operator new(0x60u);
    memset_0(v9 + 16, 0, 0x50u);
    *(_QWORD *)v9 = 0;
    *((_QWORD *)v9 + 1) = 0;
    v2 = operator new(0x30u);
    *v2 = v2;
    v2[1] = v2;
    v2[2] = v2;
    *((_WORD *)v2 + 12) = 257;
    *(_QWORD *)v9 = v2;
    *((_QWORD *)v9 + 2) = 2;
    *(_OWORD *)(v9 + 40) = 0;
    *(_OWORD *)(v9 + 56) = 0;
    *(_OWORD *)(v9 + 72) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_DWORD *)v9 + 22) = -1;
    *((_DWORD *)v9 + 23) = 0;
    v5 = (Windows::Internal::DialogBlocking::ServiceSessions *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v9;
    if ( v5 )
    {
      Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(v5);
      operator delete(v5);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v7, v3, v4);
  }
  return result;
}

```

## disassembly

```asm
0x180006890  mov     [rsp+arg_0], rbx
0x180006895  mov     [rsp+arg_18], rsi
0x18000689a  push    rdi
0x18000689b  sub     rsp, 20h
0x18000689f  mov     rsi, rcx
0x1800068a2  mov     ecx, 60h ; '`'; Size
0x1800068a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068ac  mov     rbx, rax
0x1800068af  mov     [rsp+28h+arg_8], rax
0x1800068b4  lea     rcx, [rax+10h]; void *
0x1800068b8  xor     edx, edx; Val
0x1800068ba  lea     r8d, [rdx+50h]; Size
0x1800068be  call    memset_0
0x1800068c3  mov     qword ptr [rbx], 0
0x1800068ca  mov     qword ptr [rbx+8], 0
0x1800068d2  mov     ecx, 30h ; '0'; Size
0x1800068d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068dc  mov     [rax], rax
0x1800068df  mov     [rax+8], rax
0x1800068e3  mov     [rax+10h], rax
0x1800068e7  mov     word ptr [rax+18h], 101h
0x1800068ed  mov     [rbx], rax
0x1800068f0  mov     qword ptr [rbx+10h], 2
0x1800068f8  xorps   xmm0, xmm0
0x1800068fb  movups  xmmword ptr [rbx+28h], xmm0
0x1800068ff  movups  xmmword ptr [rbx+38h], xmm0
0x180006903  movups  xmmword ptr [rbx+48h], xmm0
0x180006907  mov     qword ptr [rbx+18h], 0
0x18000690f  mov     qword ptr [rbx+20h], 0
0x180006917  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x18000691e  mov     dword ptr [rbx+5Ch], 0
0x180006925  mov     rdi, [rsi+38h]
0x180006929  mov     [rsi+38h], rbx
0x18000692d  test    rdi, rdi
0x180006930  jz      short loc_180006947
0x180006932  mov     rcx, rdi; this
0x180006935  call    ??1ServiceSessions@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(void)
0x18000693a  mov     edx, 60h ; '`'; unsigned __int64
0x18000693f  mov     rcx, rdi; void *
0x180006942  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006947  xor     eax, eax
0x180006949  jmp     short loc_18000694F
0x18000694b  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000694f  mov     rbx, [rsp+28h+arg_0]
0x180006954  mov     rsi, [rsp+28h+arg_18]
0x180006959  add     rsp, 20h
0x18000695d  pop     rdi
0x18000695e  retn
```

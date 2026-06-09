# IIS_CRYPTO_BASE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,int)

- ea: `0x1800053bc`
- end: `0x18000547a`
- name: `?Initialize@IIS_CRYPTO_BASE@@QEAAJ_K00H@Z`
- size: `190`
- prototype: `__int64 __usercall@<rax>(IIS_CRYPTO_BASE *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003538`
- `0x1800039d4`
- `0x180005900`

## callees

- `0x1800048a4`
- `0x1800053bc`
- `0x180005d6c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800053db`
- `KERNEL32!EnterCriticalSection` at `0x1800053db`
- `KERNEL32!LeaveCriticalSection` at `0x180005462`
- `KERNEL32!LeaveCriticalSection` at `0x180005462`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::Initialize(IIS_CRYPTO_BASE *this, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  const char *v8; // r8
  __int64 v9; // r9
  int ContainerHelper; // edi
  int v11; // eax

  EnterCriticalSection(&IcpGlobals);
  if ( a2 )
  {
    *(_QWORD *)this = a2;
    ContainerHelper = 0;
    v11 = 0;
  }
  else
  {
    ContainerHelper = IcpGetContainerHelper(
                        (unsigned __int64 *)this,
                        "Microsoft Internet Information Server",
                        v8,
                        v9,
                        a5 != 0 ? 0x20 : 0,
                        a5 != 0);
    v11 = 1;
  }
  *((_DWORD *)this + 2) = v11;
  if ( ContainerHelper >= 0 )
  {
    ContainerHelper = IcpGetKeyHelper((HCRYPTKEY *)this + 2, *(_QWORD *)this, 1u);
    if ( ContainerHelper >= 0 )
    {
      if ( a4 )
        *((_QWORD *)this + 3) = a4;
      else
        ContainerHelper = IcpGetKeyHelper((HCRYPTKEY *)this + 3, *(_QWORD *)this, 2u);
    }
  }
  LeaveCriticalSection(&IcpGlobals);
  return (unsigned int)ContainerHelper;
}

```

## disassembly

```asm
0x1800053bc  mov     [rsp+arg_0], rbx
0x1800053c1  mov     [rsp+arg_8], rsi
0x1800053c6  push    rdi
0x1800053c7  sub     rsp, 30h
0x1800053cb  mov     rbx, rcx
0x1800053ce  mov     rsi, r9
0x1800053d1  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x1800053d8  mov     rdi, rdx
0x1800053db  call    cs:__imp_EnterCriticalSection
0x1800053e1  test    rdi, rdi
0x1800053e4  jnz     short loc_180005418
0x1800053e6  mov     eax, [rsp+38h+arg_20]
0x1800053ea  xor     edx, edx
0x1800053ec  test    eax, eax
0x1800053ee  mov     rcx, rbx; unsigned __int64 *
0x1800053f1  setnz   dl
0x1800053f4  neg     eax
0x1800053f6  mov     [rsp+38h+var_10], edx; int
0x1800053fa  lea     rdx, aMicrosoftInter; "Microsoft Internet Information Server"
0x180005401  sbb     eax, eax
0x180005403  and     eax, 20h
0x180005406  mov     [rsp+38h+var_18], eax; unsigned int
0x18000540a  call    ?IcpGetContainerHelper@@YAJPEA_KPEBD1KKH@Z; IcpGetContainerHelper(unsigned __int64 *,char const *,char const *,ulong,ulong,int)
0x18000540f  mov     edi, eax
0x180005411  mov     eax, 1
0x180005416  jmp     short loc_18000541F
0x180005418  mov     [rbx], rdi
0x18000541b  xor     edi, edi
0x18000541d  xor     eax, eax
0x18000541f  mov     [rbx+8], eax
0x180005422  test    edi, edi
0x180005424  js      short loc_18000545B
0x180005426  mov     rdx, [rbx]; hProv
0x180005429  lea     rcx, [rbx+10h]; phKey
0x18000542d  mov     r8d, 1; Algid
0x180005433  call    ?IcpGetKeyHelper@@YAJPEA_K_KK@Z; IcpGetKeyHelper(unsigned __int64 *,unsigned __int64,ulong)
0x180005438  mov     edi, eax
0x18000543a  test    eax, eax
0x18000543c  js      short loc_18000545B
0x18000543e  test    rsi, rsi
0x180005441  jnz     short loc_180005457
0x180005443  mov     rdx, [rbx]; hProv
0x180005446  lea     r8d, [rsi+2]; Algid
0x18000544a  lea     rcx, [rbx+18h]; phKey
0x18000544e  call    ?IcpGetKeyHelper@@YAJPEA_K_KK@Z; IcpGetKeyHelper(unsigned __int64 *,unsigned __int64,ulong)
0x180005453  mov     edi, eax
0x180005455  jmp     short loc_18000545B
0x180005457  mov     [rbx+18h], rsi
0x18000545b  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180005462  call    cs:__imp_LeaveCriticalSection
0x180005468  mov     rbx, [rsp+38h+arg_0]
0x18000546d  mov     eax, edi
0x18000546f  mov     rsi, [rsp+38h+arg_8]
0x180005474  add     rsp, 30h
0x180005478  pop     rdi
0x180005479  retn
```

# ReportEventW_Client

- ea: `0x1800330ac`
- end: `0x1800333fa`
- name: `ReportEventW_Client`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800358f0`

## callees

- `0x18002cd6c`
- `0x1800330ac`
- `0x18003b7d4`
- `0x180055aa0`
- `0x180056250`
- `0x180056978`
- `0x180056a24`
- `0x180065090`

## import_xrefs

- `ntdll!RtlTimeToSecondsSince1970` at `0x1800333ae`
- `ntdll!RtlTimeToSecondsSince1970` at `0x1800333ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180033180`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180033180`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180033168`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180033168`
- `RPCRT4!RpcExceptionFilter` at `0x18006571a`
- `RPCRT4!RpcExceptionFilter` at `0x18006571a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180033323`
- `RPCRT4!I_RpcMapWin32Status` at `0x180033323`

## pseudocode

```c
__int64 __fastcall ReportEventW_Client(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int a4,
        __int64 a5,
        __int16 a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rdx
  _WORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  unsigned int v15; // esi
  __int64 v16; // r14
  char UseLegacyReportEvent; // al
  __int64 v18; // rcx
  __int64 v19; // r8
  char v20; // r15
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // eax
  ULONG ElapsedSeconds; // [rsp+8Ch] [rbp-ACh] BYREF
  LARGE_INTEGER Time; // [rsp+90h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+98h] [rbp-A0h] BYREF
  DWORD nSize; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-88h]
  __int64 v31; // [rsp+B8h] [rbp-80h]
  __int64 v32; // [rsp+C0h] [rbp-78h]
  __int64 v33; // [rsp+C8h] [rbp-70h]
  __int64 v34; // [rsp+D0h] [rbp-68h]
  _OWORD Buffer[2]; // [rsp+D8h] [rbp-60h] BYREF

  v34 = a1;
  v30 = a5;
  v31 = a8;
  v32 = a9;
  v28 = 0u;
  memset(Buffer, 0, sizeof(Buffer));
  nSize = 16;
  Time.QuadPart = 0;
  ElapsedSeconds = 0;
  GetSystemTimePreciseAsFileTime(&Time);
  GetComputerNameExW(ComputerNameNetBIOS, (LPWSTR)Buffer, &nSize);
  v28 = 0;
  v10 = 0x7FFF;
  v11 = Buffer;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = v10 == 0 ? 0xC000000D : 0;
  v13 = (0x7FFF - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
    return (unsigned int)v12;
  LOWORD(v28) = 2 * v13;
  WORD1(v28) = 2 * v13 + 2;
  *((_QWORD *)&v28 + 1) = Buffer;
  v15 = -1073741816;
  v16 = *(_QWORD *)(a1 + 8);
  v33 = v16;
  UseLegacyReportEvent = GetUseLegacyReportEvent(a1, v10, v12);
  v20 = UseLegacyReportEvent;
  v21 = *(unsigned int *)(a1 + 4);
  if ( !(_DWORD)v21 || (v21 = (unsigned int)(v21 - 1), !(_DWORD)v21) || (v22 = 0, (_DWORD)v21 == 1) )
    v22 = 1;
  if ( v22 )
  {
    if ( (byte_1800A32CD & 4) != 0 )
    {
      LOBYTE(v19) = *(_BYTE *)(a1 + 32) >> 1;
      McTemplateU0uzr0_EtwEventWriteTransfer(v18, EVENT_REPORTEVENT, v19, *(_QWORD *)(a1 + 40));
    }
  }
  else if ( (byte_1800A32CD & 4) != 0 )
  {
    LOBYTE(v19) = *(_BYTE *)(a1 + 32);
    McTemplateU0usr0_EtwEventWriteTransfer(v18, v21, v19, *(_QWORD *)(a1 + 40));
  }
  while ( v16 )
  {
    if ( v20 )
      v23 = ElfRpcReportEventW(v16, ElapsedSeconds, a2, a3, a4, a6, a7, (__int64)&v28, v30, v31, v32);
    else
      v23 = ElfRpcReportEventExW(v16, (unsigned int)&Time, a2, a3, a4, a6, a7, (__int64)&v28, v30, v31, v32);
    v15 = v23;
    if ( v23 == -1073545211 )
    {
      v16 = ReconnectToRpcServer(a1);
      v33 = v16;
    }
    else if ( v23 != -1073610706 || v20 )
    {
      v16 = 0;
      v33 = 0;
    }
    else
    {
      RtlTimeToSecondsSince1970(&Time, &ElapsedSeconds);
      *(_BYTE *)(a1 + 50) = 1;
      v20 = 1;
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800330ac  mov     r11, rsp
0x1800330af  mov     [r11+20h], r9d
0x1800330b3  push    rbx
0x1800330b4  push    rsi
0x1800330b5  push    rdi
0x1800330b6  push    r12
0x1800330b8  push    r13
0x1800330ba  push    r14
0x1800330bc  push    r15
0x1800330be  sub     rsp, 100h
0x1800330c5  mov     rax, cs:__security_cookie
0x1800330cc  xor     rax, rsp
0x1800330cf  mov     [rsp+138h+var_40], rax
0x1800330d7  mov     [rsp+138h+var_C4], r8w
0x1800330dd  mov     [rsp+138h+var_C6], dx
0x1800330e2  mov     rdi, rcx
0x1800330e5  mov     [rsp+138h+var_68], rcx
0x1800330ed  mov     [rsp+138h+var_C0], dx
0x1800330f2  mov     [rsp+138h+var_B8], r8w
0x1800330fb  mov     rax, [rsp+138h+arg_20]
0x180033103  mov     [rsp+138h+var_88], rax
0x18003310b  mov     rax, [rsp+138h+arg_38]
0x180033113  mov     [rsp+138h+var_80], rax
0x18003311b  mov     rax, [rsp+138h+arg_40]
0x180033123  mov     [rsp+138h+var_78], rax
0x18003312b  xor     ebx, ebx
0x18003312d  mov     [r11-0A0h], rbx
0x180033134  mov     [r11-98h], rbx
0x18003313b  xorps   xmm0, xmm0
0x18003313e  movups  xmmword ptr [r11-60h], xmm0
0x180033143  movups  xmmword ptr [r11-50h], xmm0
0x180033148  mov     [rsp+138h+nSize], 10h
0x180033153  mov     [r11-0A8h], rbx
0x18003315a  mov     [rsp+138h+ElapsedSeconds], ebx
0x180033161  lea     rcx, [r11-0A8h]
0x180033168  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18003316e  lea     r8, [rsp+138h+nSize]; nSize
0x180033176  lea     rdx, [rsp+138h+Buffer]; lpBuffer
0x18003317e  xor     ecx, ecx; NameType
0x180033180  call    cs:__imp_GetComputerNameExW
0x180033186  xorps   xmm0, xmm0
0x180033189  movups  [rsp+138h+var_A0], xmm0
0x180033191  mov     r9d, 7FFFh
0x180033197  mov     edx, r9d
0x18003319a  lea     rax, [rsp+138h+Buffer]
0x1800331a2  lea     r10d, [rbx+2]
0x1800331a6  cmp     [rax], bx
0x1800331a9  jz      short loc_1800331B4
0x1800331ab  add     rax, r10
0x1800331ae  sub     rdx, 1
0x1800331b2  jnz     short loc_1800331A6
0x1800331b4  mov     rax, rdx
0x1800331b7  neg     rax
0x1800331ba  sbb     r8d, r8d
0x1800331bd  not     r8d
0x1800331c0  and     r8d, 0C000000Dh
0x1800331c7  mov     rax, rdx
0x1800331ca  sub     r9, rdx
0x1800331cd  neg     rax
0x1800331d0  sbb     rcx, rcx
0x1800331d3  and     rcx, r9
0x1800331d6  test    rdx, rdx
0x1800331d9  jz      short loc_180033207
0x1800331db  add     cx, cx
0x1800331de  mov     word ptr [rsp+138h+var_A0], cx
0x1800331e6  add     cx, r10w
0x1800331ea  mov     word ptr [rsp+138h+var_A0+2], cx
0x1800331f2  lea     rax, [rsp+138h+Buffer]
0x1800331fa  mov     qword ptr [rsp+138h+var_A0+8], rax
0x180033202  test    rdx, rdx
0x180033205  jnz     short loc_18003320F
0x180033207  mov     eax, r8d
0x18003320a  jmp     loc_1800333D7
0x18003320f  mov     esi, 0C0000008h
0x180033214  mov     r14, [rdi+8]
0x180033218  mov     [rsp+138h+var_70], r14
0x180033220  mov     rcx, rdi
0x180033223  call    GetUseLegacyReportEvent
0x180033228  mov     r15b, al
0x18003322b  mov     [rsp+138h+var_C8], al
0x18003322f  mov     edx, [rdi+4]
0x180033232  test    edx, edx
0x180033234  jz      short loc_180033242
0x180033236  sub     edx, 1
0x180033239  jz      short loc_180033242
0x18003323b  cmp     edx, 1
0x18003323e  mov     eax, ebx
0x180033240  jnz     short loc_180033247
0x180033242  mov     eax, 1
0x180033247  test    eax, eax
0x180033249  jz      short loc_18003326D
0x18003324b  test    cs:byte_1800A32CD, 4
0x180033252  jz      short loc_180033283
0x180033254  mov     r8b, [rdi+20h]
0x180033258  shr     r8b, 1
0x18003325b  mov     r9, [rdi+28h]
0x18003325f  lea     rdx, EVENT_REPORTEVENT
0x180033266  call    McTemplateU0uzr0_EtwEventWriteTransfer
0x18003326b  jmp     short loc_180033283
0x18003326d  test    cs:byte_1800A32CD, 4
0x180033274  jz      short loc_180033283
0x180033276  mov     r9, [rdi+28h]
0x18003327a  mov     r8b, [rdi+20h]
0x18003327e  call    McTemplateU0usr0_EtwEventWriteTransfer
0x180033283  mov     r12d, [rsp+138h+arg_30]
0x18003328b  movzx   r13d, [rsp+138h+arg_28]
0x180033294  test    r14, r14
0x180033297  jz      loc_1800333D5
0x18003329d  mov     rax, [rsp+138h+var_78]
0x1800332a5  movzx   r9d, [rsp+138h+var_C4]
0x1800332ab  movzx   r8d, [rsp+138h+var_C6]
0x1800332b1  mov     rcx, r14
0x1800332b4  mov     [rsp+138h+var_E8], rax
0x1800332b9  mov     rax, [rsp+138h+var_80]
0x1800332c1  mov     [rsp+138h+var_F0], rax
0x1800332c6  mov     rax, [rsp+138h+var_88]
0x1800332ce  mov     [rsp+138h+var_F8], rax
0x1800332d3  lea     rax, [rsp+138h+var_A0]
0x1800332db  mov     [rsp+138h+var_100], rax
0x1800332e0  mov     [rsp+138h+var_108], r12d
0x1800332e5  mov     eax, [rsp+138h+arg_18]
0x1800332ec  mov     [rsp+138h+var_110], r13w
0x1800332f2  mov     [rsp+138h+var_118], eax
0x1800332f6  test    r15b, r15b
0x1800332f9  jnz     short loc_18003330A
0x1800332fb  lea     rdx, [rsp+138h+Time]
0x180033303  call    ElfRpcReportEventExW
0x180033308  jmp     short loc_180033316
0x18003330a  mov     edx, [rsp+138h+ElapsedSeconds]
0x180033311  call    ElfRpcReportEventW
0x180033316  mov     [rsp+138h+var_B0], eax
0x18003331d  mov     esi, eax
0x18003331f  jmp     short loc_180033371
0x180033321  mov     ecx, eax; Status
0x180033323  call    cs:__imp_I_RpcMapWin32Status
0x180033329  mov     esi, eax
0x18003332b  mov     [rsp+138h+var_B0], eax
0x180033332  xor     ebx, ebx
0x180033334  mov     r12d, [rsp+138h+arg_30]
0x18003333c  movzx   r13d, [rsp+138h+arg_28]
0x180033345  mov     r14, [rsp+138h+var_70]
0x18003334d  mov     r15b, [rsp+138h+var_C8]
0x180033352  mov     rdi, [rsp+138h+var_68]
0x18003335a  movzx   eax, [rsp+138h+var_C0]
0x18003335f  mov     [rsp+138h+var_C6], ax
0x180033364  movzx   eax, [rsp+138h+var_B8]
0x18003336c  mov     [rsp+138h+var_C4], ax
0x180033371  cmp     esi, 0C0030005h
0x180033377  jnz     short loc_180033391
0x180033379  mov     rcx, rdi
0x18003337c  call    ReconnectToRpcServer
0x180033381  mov     r14, rax
0x180033384  mov     [rsp+138h+var_70], rax
0x18003338c  jmp     loc_180033294
0x180033391  cmp     esi, 0C002002Eh
0x180033397  jnz     short loc_1800333C5
0x180033399  test    r15b, r15b
0x18003339c  jnz     short loc_1800333C5
0x18003339e  lea     rdx, [rsp+138h+ElapsedSeconds]; ElapsedSeconds
0x1800333a6  lea     rcx, [rsp+138h+Time]; Time
0x1800333ae  call    cs:__imp_RtlTimeToSecondsSince1970
0x1800333b4  mov     byte ptr [rdi+32h], 1
0x1800333b8  mov     r15b, 1
0x1800333bb  mov     [rsp+138h+var_C8], r15b
0x1800333c0  jmp     loc_180033294
0x1800333c5  mov     r14, rbx
0x1800333c8  mov     [rsp+138h+var_70], rbx
0x1800333d0  jmp     loc_180033294
0x1800333d5  mov     eax, esi
0x1800333d7  mov     rcx, [rsp+138h+var_40]
0x1800333df  xor     rcx, rsp; StackCookie
0x1800333e2  call    __security_check_cookie
0x1800333e7  add     rsp, 100h
0x1800333ee  pop     r15
0x1800333f0  pop     r14
0x1800333f2  pop     r13
0x1800333f4  pop     r12
0x1800333f6  pop     rdi
0x1800333f7  pop     rsi
0x1800333f8  pop     rbx
0x1800333f9  retn
0x18006570c  push    rbp
0x18006570e  sub     rsp, 70h
0x180065712  mov     rbp, rdx
0x180065715  mov     rcx, [rcx]
0x180065718  mov     ecx, [rcx]; ExceptionCode
0x18006571a  call    cs:__imp_RpcExceptionFilter
0x180065720  nop
0x180065721  add     rsp, 70h
0x180065725  pop     rbp
0x180065726  retn
```

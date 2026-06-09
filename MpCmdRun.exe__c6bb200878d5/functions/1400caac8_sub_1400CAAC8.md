# sub_1400CAAC8

- ea: `0x1400caac8`
- end: `0x1400cad54`
- name: `sub_1400CAAC8`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400d0538`

## callees

- `0x140036780`
- `0x1400368dc`
- `0x1400751c8`
- `0x14007f288`
- `0x1400caac8`
- `0x1400df4bc`
- `0x1401203c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400cabdf`
- `KERNEL32!GetLastError` at `0x1400cabdf`
- `KERNEL32!SetLastError` at `0x1400cabf2`
- `KERNEL32!SetLastError` at `0x1400cabf2`
- `ADVAPI32!CloseTrace` at `0x1400cabea`
- `ADVAPI32!CloseTrace` at `0x1400cac00`
- `ADVAPI32!CloseTrace` at `0x1400cabea`
- `ADVAPI32!CloseTrace` at `0x1400cac00`
- `ADVAPI32!OpenTraceW` at `0x1400caba7`
- `ADVAPI32!OpenTraceW` at `0x1400caba7`

## pseudocode

```c
__int64 __fastcall sub_1400CAAC8(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v9; // r8
  WCHAR *v10; // rax
  TRACEHANDLE v11; // r14
  TRACEHANDLE v12; // rdi
  DWORD LastError; // ebx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  char v20; // [rsp+40h] [rbp-C0h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+210h] [rbp+110h] BYREF
  __int128 v23; // [rsp+220h] [rbp+120h]
  void *retaddr; // [rsp+278h] [rbp+178h]

  *(_QWORD *)a1 = -1;
  *(_DWORD *)(a1 + 8) = 0;
  sub_1401203C0(&Logfile, 0, 448);
  v22 = 0;
  v23 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a2 + 2 * v9) );
  sub_1400751C8(&v22, a2, v9);
  v10 = (WCHAR *)&v22;
  if ( *((_QWORD *)&v23 + 1) > 7u )
    v10 = (WCHAR *)v22;
  Logfile.LogFileName = v10;
  Logfile.LogFileMode = 0x10000000;
  Logfile.EventCallback = (PEVENT_CALLBACK)sub_1400D3A00;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)sub_1400D2A10;
  Logfile.Context = (PVOID)a1;
  v11 = OpenTraceW(&Logfile);
  if ( v11 == -1 )
    sub_1400DF4BC(retaddr);
  sub_14007F288(&v22);
  if ( (char *)a1 == &v20 )
  {
    CloseTrace(v11);
  }
  else
  {
    v12 = *(_QWORD *)a1;
    if ( *(_QWORD *)a1 != -1 )
    {
      LastError = GetLastError();
      CloseTrace(v12);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v14 = operator new(0x110u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *(_QWORD *)(a1 + 16) = v14;
  *(_QWORD *)(a1 + 40) = a5;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v15 = operator new(0xD0u);
  *v15 = v15;
  v15[1] = v15;
  v15[2] = v15;
  *((_WORD *)v15 + 12) = 257;
  *(_QWORD *)(a1 + 48) = v15;
  *(_QWORD *)(a1 + 72) = a5;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  v16 = operator new(0xA0u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  *(_QWORD *)(a1 + 80) = v16;
  *(_QWORD *)(a1 + 104) = a5;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  v17 = operator new(0xA8u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  *(_QWORD *)(a1 + 112) = v17;
  *(_QWORD *)(a1 + 136) = a5;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  v18 = operator new(0xD0u);
  *v18 = v18;
  v18[1] = v18;
  v18[2] = v18;
  *((_WORD *)v18 + 12) = 257;
  *(_QWORD *)(a1 + 144) = v18;
  *(_QWORD *)(a1 + 168) = a5;
  *(_QWORD *)(a1 + 176) = a3;
  *(_BYTE *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = a4;
  *(_BYTE *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0x8000000000000000uLL;
  return a1;
}

```

## disassembly

```asm
0x1400caac8  mov     [rsp-8+arg_10], rbx
0x1400caacd  push    rbp
0x1400caace  push    rsi
0x1400caacf  push    rdi
0x1400caad0  push    r12
0x1400caad2  push    r13
0x1400caad4  push    r14
0x1400caad6  push    r15
0x1400caad8  lea     rbp, [rsp-140h]
0x1400caae0  sub     rsp, 240h
0x1400caae7  mov     rax, cs:__security_cookie
0x1400caaee  xor     rax, rsp
0x1400caaf1  mov     [rbp+170h+var_40], rax
0x1400caaf8  mov     r15, r9
0x1400caafb  mov     r12, r8
0x1400caafe  mov     rbx, rdx
0x1400cab01  mov     rsi, rcx
0x1400cab04  mov     [rsp+270h+var_240], rcx
0x1400cab09  xor     r13d, r13d
0x1400cab0c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400cab10  mov     [rcx], rdi
0x1400cab13  mov     [rcx+8], r13d
0x1400cab17  xor     edx, edx
0x1400cab19  mov     r8d, 1C0h
0x1400cab1f  lea     rcx, [rsp+270h+Logfile]
0x1400cab24  call    sub_1401203C0
0x1400cab29  xorps   xmm0, xmm0
0x1400cab2c  movups  [rbp+170h+var_60], xmm0
0x1400cab33  xorps   xmm1, xmm1
0x1400cab36  movdqu  [rbp+170h+var_50], xmm1
0x1400cab3e  mov     r8, rdi
0x1400cab41  inc     r8
0x1400cab44  cmp     [rbx+r8*2], r13w
0x1400cab49  jnz     short loc_1400CAB41
0x1400cab4b  mov     rdx, rbx
0x1400cab4e  lea     rcx, [rbp+170h+var_60]
0x1400cab55  call    sub_1400751C8
0x1400cab5a  nop
0x1400cab5b  lea     rax, [rbp+170h+var_60]
0x1400cab62  cmp     qword ptr [rbp+170h+var_50+8], 7
0x1400cab6a  cmova   rax, qword ptr [rbp+170h+var_60]
0x1400cab72  mov     [rsp+270h+Logfile.LogFileName], rax
0x1400cab77  mov     dword ptr [rsp+270h+Logfile.1Ch], 10000000h
0x1400cab7f  lea     rax, sub_1400D3A00
0x1400cab86  mov     qword ptr [rbp+170h+Logfile.1A8h], rax
0x1400cab8d  lea     rax, sub_1400D2A10
0x1400cab94  mov     [rbp+170h+Logfile.BufferCallback], rax
0x1400cab9b  mov     [rbp+170h+Logfile.Context], rsi
0x1400caba2  lea     rcx, [rsp+270h+Logfile]; Logfile
0x1400caba7  call    cs:OpenTraceW
0x1400cabad  mov     r14, rax
0x1400cabb0  mov     rcx, [rbp+178h]
0x1400cabb7  cmp     rax, rdi
0x1400cabba  jz      loc_1400CAD4E
0x1400cabc0  lea     rcx, [rbp+170h+var_60]
0x1400cabc7  call    sub_14007F288
0x1400cabcc  lea     rax, [rsp+270h+var_230]
0x1400cabd1  cmp     rsi, rax
0x1400cabd4  jz      short loc_1400CABFD
0x1400cabd6  mov     rdi, [rsi]
0x1400cabd9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400cabdd  jz      short loc_1400CABF8
0x1400cabdf  call    cs:GetLastError
0x1400cabe5  mov     ebx, eax
0x1400cabe7  mov     rcx, rdi; TraceHandle
0x1400cabea  call    cs:CloseTrace
0x1400cabf0  mov     ecx, ebx; dwErrCode
0x1400cabf2  call    cs:SetLastError
0x1400cabf8  mov     [rsi], r14
0x1400cabfb  jmp     short loc_1400CAC07
0x1400cabfd  mov     rcx, r14; TraceHandle
0x1400cac00  call    cs:CloseTrace
0x1400cac06  nop
0x1400cac07  mov     [rsi+10h], r13
0x1400cac0b  mov     [rsi+18h], r13
0x1400cac0f  mov     ecx, 110h; Size
0x1400cac14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cac19  mov     [rax], rax
0x1400cac1c  mov     [rax+8], rax
0x1400cac20  mov     [rax+10h], rax
0x1400cac24  mov     word ptr [rax+18h], 101h
0x1400cac2a  mov     [rsi+10h], rax
0x1400cac2e  mov     rdi, [rbp+170h+arg_20]
0x1400cac35  mov     [rsi+28h], rdi
0x1400cac39  mov     [rsi+30h], r13
0x1400cac3d  mov     [rsi+38h], r13
0x1400cac41  mov     r14d, 0D0h
0x1400cac47  mov     ecx, r14d; Size
0x1400cac4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cac4f  mov     [rax], rax
0x1400cac52  mov     [rax+8], rax
0x1400cac56  mov     [rax+10h], rax
0x1400cac5a  mov     word ptr [rax+18h], 101h
0x1400cac60  mov     [rsi+30h], rax
0x1400cac64  mov     [rsi+48h], rdi
0x1400cac68  mov     [rsi+50h], r13
0x1400cac6c  mov     [rsi+58h], r13
0x1400cac70  lea     ecx, [r14-30h]; Size
0x1400cac74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cac79  mov     [rax], rax
0x1400cac7c  mov     [rax+8], rax
0x1400cac80  mov     [rax+10h], rax
0x1400cac84  mov     word ptr [rax+18h], 101h
0x1400cac8a  mov     [rsi+50h], rax
0x1400cac8e  mov     [rsi+68h], rdi
0x1400cac92  mov     [rsi+70h], r13
0x1400cac96  mov     [rsi+78h], r13
0x1400cac9a  lea     ecx, [r14-28h]; Size
0x1400cac9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400caca3  mov     [rax], rax
0x1400caca6  mov     [rax+8], rax
0x1400cacaa  mov     [rax+10h], rax
0x1400cacae  mov     word ptr [rax+18h], 101h
0x1400cacb4  mov     [rsi+70h], rax
0x1400cacb8  mov     [rsi+88h], rdi
0x1400cacbf  lea     rbx, [rsi+90h]
0x1400cacc6  mov     [rbx], r13
0x1400cacc9  mov     [rbx+8], r13
0x1400caccd  mov     ecx, r14d; Size
0x1400cacd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cacd5  mov     [rax], rax
0x1400cacd8  mov     [rax+8], rax
0x1400cacdc  mov     [rax+10h], rax
0x1400cace0  mov     word ptr [rax+18h], 101h
0x1400cace6  mov     [rbx], rax
0x1400cace9  mov     [rbx+18h], rdi
0x1400caced  mov     [rsi+0B0h], r12
0x1400cacf4  mov     [rsi+0C0h], r13b
0x1400cacfb  mov     [rsi+0C8h], r15
0x1400cad02  mov     [rsi+0D0h], r13b
0x1400cad09  mov     [rsi+0D8h], r13
0x1400cad10  mov     rax, 8000000000000000h
0x1400cad1a  mov     [rsi+0E0h], rax
0x1400cad21  mov     rax, rsi
0x1400cad24  mov     rcx, [rbp+170h+var_40]
0x1400cad2b  xor     rcx, rsp; StackCookie
0x1400cad2e  call    __security_check_cookie
0x1400cad33  mov     rbx, [rsp+270h+arg_10]
0x1400cad3b  add     rsp, 240h
0x1400cad42  pop     r15
0x1400cad44  pop     r14
0x1400cad46  pop     r13
0x1400cad48  pop     r12
0x1400cad4a  pop     rdi
0x1400cad4b  pop     rsi
0x1400cad4c  pop     rbp
0x1400cad4d  retn
0x1400cad4e  call    sub_1400DF4BC
```

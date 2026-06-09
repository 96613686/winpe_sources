# HandlerProc

- ea: `0x140043950`
- end: `0x140043c1f`
- name: `HandlerProc`
- size: `719`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140022068`

## callees

- `0x140017a8c`
- `0x140017b78`
- `0x140021f50`
- `0x140022660`
- `0x14002c880`
- `0x140032748`
- `0x140032798`
- `0x1400328c0`
- `0x140043950`
- `0x140043f64`
- `0x14004f4e0`
- `0x1400579a0`
- `0x140057d54`
- `0x140057db0`
- `0x1400b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140043be0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140043be0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140043ae1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140043ae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043aff`

## string_xrefs

- `0x140043b63`: `"onecoreuap\\base\\appmodel\\search\\common\\dcomsvc\\dcomsvc.cxx"`
- `0x140043b57`: `[UtilCommon] Service Stopping\n`

## pseudocode

```c
__int64 __fastcall HandlerProc(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, LPVOID lpContext)
{
  __int64 v7; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r8
  __int64 v10; // rax
  HANDLE Thread; // rax
  __int64 v12; // r8
  PVOID v13; // rcx
  int v15; // [rsp+30h] [rbp-48h] BYREF
  __int128 v16; // [rsp+38h] [rbp-40h] BYREF

  if ( (byte_1400E4681 & 8) != 0 )
    sub_140017A8C(&CallbackContext, qword_1400C07B8, dwControl);
  switch ( dwControl )
  {
    case 1u:
      goto LABEL_36;
    case 4u:
      sub_140032748();
      goto LABEL_42;
    case 5u:
      goto LABEL_36;
    case 0xBu:
      sub_1400B2010(pv, 11, dwEventType);
      goto LABEL_42;
    case 0xDu:
      if ( dwEventType == 4 || dwEventType == 7 )
        sub_140043F64();
      goto LABEL_42;
  }
  if ( dwControl != 14 )
  {
    if ( dwControl != 15 )
    {
      if ( dwControl != 33 )
      {
        sub_1400328C0(pv);
        goto LABEL_42;
      }
      goto LABEL_12;
    }
LABEL_36:
    sub_140021F50(
      L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\dcomsvc\\\\dcomsvc.cxx\"",
      933,
      L"[UtilCommon] Service Stopping\n");
    if ( (byte_1400E4682 & 8) != 0 )
      sub_140017B78(&CallbackContext, qword_1400C07C8, v12, 1, &v16);
    v15 = (dwControl != 1) + 1;
    sub_14004F4E0(&v15);
    v13 = pv;
    if ( dwControl == 5 || dwControl == 15 )
      *((_BYTE *)pv + 296) = 1;
    sub_140032798(v13, 3);
    SetEvent(*((HANDLE *)pv + 11));
    goto LABEL_42;
  }
LABEL_12:
  if ( !(unsigned __int8)sub_140022660() )
    goto LABEL_18;
  if ( dwEventType == 5 && dwControl != 33 )
    goto LABEL_42;
  if ( dwEventType == 6 )
  {
    if ( dwControl != 14 )
      goto LABEL_42;
  }
  else
  {
LABEL_18:
    if ( dwEventType - 5 > 1 )
      goto LABEL_42;
  }
  v7 = sub_140057DB0(24, qword_1400BE180);
  v8 = (_QWORD *)v7;
  if ( v7 )
  {
    *(_DWORD *)(v7 + 12) = 0;
    *(_DWORD *)(v7 + 8) = -1;
    *(_QWORD *)(v7 + 16) = 0;
    *(_DWORD *)v7 = dwControl;
    *(_DWORD *)(v7 + 4) = dwEventType;
    if ( dwControl == 14 )
    {
      if ( (unsigned __int8)sub_140022660() )
      {
        v10 = sub_1400B2010(pv, *((unsigned int *)lpEventData + 1), v9);
        v8[1] = *((unsigned int *)lpEventData + 1);
        v8[2] = v10;
      }
    }
    else
    {
      *(_QWORD *)&v16 = *((unsigned int *)lpEventData + 1);
      *((_QWORD *)&v16 + 1) = lpEventData[1];
      *(_OWORD *)(v7 + 8) = v16;
    }
    if ( v8[2] )
    {
      if ( (unsigned __int8)sub_140022660() && dwEventType == 6 )
      {
        StartAddress(v8);
      }
      else
      {
        Thread = CreateThread(0, 0, StartAddress, v8, 0, 0);
        if ( Thread )
          CloseHandle(Thread);
        else
          j_j__o_free(v8, 24);
      }
    }
  }
LABEL_42:
  if ( (byte_1400E4681 & 8) != 0 )
    sub_140017A8C(&CallbackContext, qword_1400C07A8, dwControl);
  return 0;
}

```

## disassembly

```asm
0x140043950  push    rbx
0x140043952  push    rbp
0x140043953  push    rsi
0x140043954  push    rdi
0x140043955  push    r14
0x140043957  sub     rsp, 50h
0x14004395b  mov     rax, cs:__security_cookie
0x140043962  xor     rax, rsp
0x140043965  mov     [rsp+78h+var_30], rax
0x14004396a  test    cs:byte_1400E4681, 8
0x140043971  mov     rbx, r9
0x140043974  mov     r14, r8
0x140043977  mov     ebp, edx
0x140043979  mov     esi, ecx
0x14004397b  jz      short loc_140043993
0x14004397d  mov     r8d, ecx
0x140043980  lea     rdx, qword_1400C07B8
0x140043987  lea     rcx, CallbackContext
0x14004398e  call    sub_140017A8C
0x140043993  mov     eax, esi
0x140043995  sub     eax, 1
0x140043998  jz      loc_140043B57
0x14004399e  sub     eax, 3
0x1400439a1  jz      loc_140043B4D
0x1400439a7  sub     eax, 1
0x1400439aa  jz      loc_140043B57
0x1400439b0  sub     eax, 6
0x1400439b3  jz      loc_140043B22
0x1400439b9  sub     eax, 2
0x1400439bc  jz      loc_140043B0A
0x1400439c2  sub     eax, 1
0x1400439c5  jz      short loc_1400439E6
0x1400439c7  sub     eax, 1
0x1400439ca  jz      loc_140043B57
0x1400439d0  cmp     eax, 12h
0x1400439d3  jz      short loc_1400439E6
0x1400439d5  mov     rcx, cs:pv
0x1400439dc  call    sub_1400328C0
0x1400439e1  jmp     loc_140043BE6
0x1400439e6  call    sub_140022660
0x1400439eb  xor     ebx, ebx
0x1400439ed  test    al, al
0x1400439ef  jz      short loc_140043A0E
0x1400439f1  cmp     ebp, 5
0x1400439f4  jnz     short loc_1400439FF
0x1400439f6  cmp     esi, 21h ; '!'
0x1400439f9  jnz     loc_140043BE6
0x1400439ff  cmp     ebp, 6
0x140043a02  jnz     short loc_140043A0E
0x140043a04  cmp     esi, 0Eh
0x140043a07  jz      short loc_140043A1A
0x140043a09  jmp     loc_140043BE6
0x140043a0e  lea     eax, [rbp-5]
0x140043a11  cmp     eax, 1
0x140043a14  ja      loc_140043BE6
0x140043a1a  lea     rdx, qword_1400BE180
0x140043a21  mov     ecx, 18h
0x140043a26  call    sub_140057DB0
0x140043a2b  mov     rdi, rax
0x140043a2e  test    rax, rax
0x140043a31  jz      loc_140043BE6
0x140043a37  mov     [rax+0Ch], ebx
0x140043a3a  mov     dword ptr [rax+8], 0FFFFFFFFh
0x140043a41  mov     [rax+10h], rbx
0x140043a45  mov     [rax], esi
0x140043a47  mov     [rax+4], ebp
0x140043a4a  cmp     esi, 0Eh
0x140043a4d  jnz     short loc_140043A84
0x140043a4f  call    sub_140022660
0x140043a54  test    al, al
0x140043a56  jz      short loc_140043AA5
0x140043a58  mov     rcx, cs:pv
0x140043a5f  mov     edx, [r14+4]
0x140043a63  mov     rax, [rcx]
0x140043a66  mov     rax, [rax+0B0h]
0x140043a6d  call    sub_1400B2010
0x140043a72  mov     ecx, [r14+4]
0x140043a76  xor     edx, edx
0x140043a78  mov     [rdi+0Ch], edx
0x140043a7b  mov     [rdi+8], ecx
0x140043a7e  mov     [rdi+10h], rax
0x140043a82  jmp     short loc_140043AA5
0x140043a84  mov     eax, [r14+4]
0x140043a88  mov     dword ptr [rsp+78h+var_40], eax
0x140043a8c  xor     eax, eax
0x140043a8e  mov     dword ptr [rsp+78h+var_40+4], eax
0x140043a92  mov     rax, [r14+8]
0x140043a96  mov     qword ptr [rsp+78h+var_40+8], rax
0x140043a9b  movups  xmm0, [rsp+78h+var_40]
0x140043aa0  movdqu  xmmword ptr [rdi+8], xmm0
0x140043aa5  cmp     [rdi+10h], rbx
0x140043aa9  jz      loc_140043BE6
0x140043aaf  call    sub_140022660
0x140043ab4  test    al, al
0x140043ab6  jz      short loc_140043ACA
0x140043ab8  cmp     ebp, 6
0x140043abb  jnz     short loc_140043ACA
0x140043abd  mov     rcx, rdi; Parameter
0x140043ac0  call    StartAddress
0x140043ac5  jmp     loc_140043BE6
0x140043aca  mov     [rsp+78h+lpThreadId], rbx; lpThreadId
0x140043acf  lea     r8, StartAddress; lpStartAddress
0x140043ad6  mov     r9, rdi; lpParameter
0x140043ad9  mov     [rsp+78h+dwCreationFlags], ebx; dwCreationFlags
0x140043add  xor     edx, edx; dwStackSize
0x140043adf  xor     ecx, ecx; lpThreadAttributes
0x140043ae1  call    cs:CreateThread
0x140043ae7  test    rax, rax
0x140043aea  jnz     short loc_140043AFC
0x140043aec  lea     edx, [rax+18h]
0x140043aef  mov     rcx, rdi
0x140043af2  call    j_j__o_free
0x140043af7  jmp     loc_140043BE6
0x140043afc  mov     rcx, rax; hObject
0x140043aff  call    cs:CloseHandle
0x140043b05  jmp     loc_140043BE6
0x140043b0a  cmp     ebp, 4
0x140043b0d  jz      short loc_140043B18
0x140043b0f  cmp     ebp, 7
0x140043b12  jnz     loc_140043BE6
0x140043b18  call    sub_140043F64
0x140043b1d  jmp     loc_140043BE6
0x140043b22  mov     rcx, cs:pv
0x140043b29  mov     r9, r14
0x140043b2c  mov     r8d, ebp
0x140043b2f  mov     qword ptr [rsp+78h+dwCreationFlags], rbx
0x140043b34  mov     edx, 0Bh
0x140043b39  mov     rax, [rcx]
0x140043b3c  mov     rax, [rax+0A0h]
0x140043b43  call    sub_1400B2010
0x140043b48  jmp     loc_140043BE6
0x140043b4d  call    sub_140032748
0x140043b52  jmp     loc_140043BE6
0x140043b57  lea     r8, aUtilcommonServ; "[UtilCommon] Service Stopping\n"
0x140043b5e  mov     edx, 3A5h
0x140043b63  lea     rcx, aOnecoreuapBase_29; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140043b6a  call    sub_140021F50
0x140043b6f  test    cs:byte_1400E4682, 8
0x140043b76  jz      short loc_140043B9B
0x140043b78  lea     rax, [rsp+78h+var_40]
0x140043b7d  mov     r9d, 1
0x140043b83  lea     rdx, qword_1400C07C8
0x140043b8a  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x140043b8f  lea     rcx, CallbackContext
0x140043b96  call    sub_140017B78
0x140043b9b  xor     ebx, ebx
0x140043b9d  lea     rcx, [rsp+78h+var_48]
0x140043ba2  cmp     esi, 1
0x140043ba5  setnz   bl
0x140043ba8  inc     ebx
0x140043baa  mov     [rsp+78h+var_48], ebx
0x140043bae  call    sub_14004F4E0
0x140043bb3  mov     rcx, cs:pv
0x140043bba  cmp     esi, 5
0x140043bbd  jz      short loc_140043BC4
0x140043bbf  cmp     esi, 0Fh
0x140043bc2  jnz     short loc_140043BCB
0x140043bc4  mov     byte ptr [rcx+128h], 1
0x140043bcb  mov     edx, 3
0x140043bd0  call    sub_140032798
0x140043bd5  mov     rcx, cs:pv
0x140043bdc  mov     rcx, [rcx+58h]; hEvent
0x140043be0  call    cs:SetEvent
0x140043be6  test    cs:byte_1400E4681, 8
0x140043bed  jz      short loc_140043C05
0x140043bef  mov     r8d, esi
0x140043bf2  lea     rdx, qword_1400C07A8
0x140043bf9  lea     rcx, CallbackContext
0x140043c00  call    sub_140017A8C
0x140043c05  xor     eax, eax
0x140043c07  mov     rcx, [rsp+78h+var_30]
0x140043c0c  xor     rcx, rsp; StackCookie
0x140043c0f  call    __security_check_cookie
0x140043c14  add     rsp, 50h
0x140043c18  pop     r14
0x140043c1a  pop     rdi
0x140043c1b  pop     rsi
0x140043c1c  pop     rbp
0x140043c1d  pop     rbx
0x140043c1e  retn
```

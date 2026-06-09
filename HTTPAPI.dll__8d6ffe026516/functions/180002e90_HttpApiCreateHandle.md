# HttpApiCreateHandle

- ea: `0x180002e90`
- end: `0x18000333f`
- name: `HttpApiCreateHandle`
- size: `1199`
- prototype: `__int64 __fastcall(int, int, int, int, STRSAFE_LPCWSTR pszSrc, int, ULONG, ULONG, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004090`

## callees

- `0x180002e90`
- `0x180004400`
- `0x18000a4bc`
- `0x18000a4c8`
- `0x18000a5f0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003189`
- `ntdll!RtlFreeHeap` at `0x180003189`
- `ntdll!RtlAllocateHeap` at `0x180003071`
- `ntdll!RtlAllocateHeap` at `0x180003071`
- `ntdll!NtCreateFile` at `0x180003167`
- `ntdll!NtCreateFile` at `0x180003167`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003048`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003334`

## string_xrefs

- `0x180002f5b`: `\Device\Http\Communication`
- `0x1800030bb`: `UlOpenPacket000`

## pseudocode

```c
__int64 __fastcall HttpApiCreateHandle(
        HANDLE *a1,
        unsigned int a2,
        ACCESS_MASK a3,
        int a4,
        STRSAFE_LPCWSTR pszSrc,
        int a6,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        __int64 a9,
        int a10,
        __int64 a11)
{
  __int16 v11; // bx
  unsigned int v14; // r13d
  const void *v15; // r12
  __int64 v16; // r11
  const wchar_t *v17; // rdx
  wchar_t *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r9
  wchar_t *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  size_t v25; // rcx
  NTSTATUS inited; // edi
  char *Heap; // rax
  char *EaBuffer; // rsi
  ULONG v29; // ecx
  size_t v30; // rdx
  wchar_t *v31; // rax
  int v32; // edi
  const wchar_t *v33; // r8
  wchar_t *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  const wchar_t *v37; // r8
  __int64 v38; // rcx
  wchar_t *v39; // rax
  size_t v40; // r10
  wchar_t *v41; // rcx
  bool v42; // zf
  HANDLE FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-98h]
  ACCESS_MASK DesiredAccess; // [rsp+6Ch] [rbp-94h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t pszDest[288]; // [rsp+D0h] [rbp-30h] BYREF

  v11 = a2;
  v44 = HIWORD(a2);
  DesiredAccess = a3;
  v46 = a9;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  memset_0(pszDest, 0, sizeof(pszDest));
  if ( !a1 )
    return 3221225485LL;
  if ( a11 )
  {
    if ( a10 != 1 )
      return 3221225485LL;
    v14 = *(_DWORD *)(a11 + 4);
    v15 = *(const void **)(a11 + 8);
  }
  else
  {
    v14 = 0;
    v15 = 0;
  }
  *a1 = 0;
  if ( a4 )
  {
    v32 = a4 - 1;
    if ( !v32 )
    {
      v16 = 2147483646;
      v33 = L"\\Device\\Http\\ReqQueue";
      v34 = pszDest;
      v35 = 2147483646;
      v36 = 288;
      while ( v35 && *v33 )
      {
        *v34++ = *v33++;
        --v35;
        if ( !--v36 )
        {
          v21 = v34 - 1;
          goto LABEL_11;
        }
      }
      goto LABEL_42;
    }
    if ( v32 == 1 )
    {
      v16 = 2147483646;
      v37 = L"\\Device\\Http\\ClientSession";
      v34 = pszDest;
      v38 = 2147483646;
      v36 = 288;
      do
      {
        if ( !v38 )
          break;
        if ( !*v37 )
          break;
        *v34++ = *v37++;
        --v38;
        --v36;
      }
      while ( v36 );
LABEL_42:
      v21 = v34 - 1;
      if ( v36 )
        v21 = v34;
      goto LABEL_11;
    }
    return 3221225485LL;
  }
  v16 = 2147483646;
  v17 = L"\\Device\\Http\\Communication";
  v18 = pszDest;
  v19 = 2147483646;
  v20 = 288;
  do
  {
    if ( !v19 )
      break;
    if ( !*v17 )
      break;
    *v18++ = *v17++;
    --v19;
    --v20;
  }
  while ( v20 );
  v21 = v18 - 1;
  if ( v20 )
    v21 = v18;
LABEL_11:
  *v21 = 0;
  if ( pszSrc )
  {
    v22 = -1;
    v23 = -1;
    do
      ++v23;
    while ( pszDest[v23] );
    do
      ++v22;
    while ( pszSrc[v22] );
    if ( (unsigned __int64)(v23 + v22 + 2) > 0x120 )
      return 3221225485LL;
    v30 = 288;
    v31 = pszDest;
    do
    {
      if ( !*v31 )
        break;
      ++v31;
      --v30;
    }
    while ( v30 );
    v25 = 288 - v30;
    if ( v30 )
    {
      v39 = &pszDest[v25];
      v30 = (size_t)L"\\";
      v40 = 288 - v25;
      if ( 288 != v25 )
      {
        do
        {
          if ( !v16 )
            break;
          if ( !*(_WORD *)v30 )
            break;
          *v39 = *(_WORD *)v30;
          v30 += 2LL;
          ++v39;
          --v16;
          --v40;
        }
        while ( v40 );
      }
      v41 = v39 - 1;
      if ( v40 )
        v41 = v39;
      *v41 = 0;
    }
    StringCchCatW(pszDest, v30, pszSrc);
  }
  inited = RtlInitUnicodeStringEx(&DestinationString, pszDest);
  if ( inited >= 0 )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14 + 51);
    EaBuffer = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, v14 + 51);
      *((_WORD *)EaBuffer + 2) = 3840;
      if ( (unsigned __int64)v14 + 24 >= 0xFFFF )
      {
        inited = -1073741811;
      }
      else
      {
        *(_DWORD *)EaBuffer = 0;
        *((_WORD *)EaBuffer + 3) = v14 + 24;
        strcpy(EaBuffer + 8, "UlOpenPacket000");
        *((_WORD *)EaBuffer + 13) = v44;
        *((_DWORD *)EaBuffer + 7) = a6;
        *((_WORD *)EaBuffer + 12) = v11;
        *((_QWORD *)EaBuffer + 4) = g_CommunicationChannel;
        *((_DWORD *)EaBuffer + 10) = v14;
        memcpy_0(EaBuffer + 44, v15, v14);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        v29 = 64;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( v46 )
        {
          v42 = *(_DWORD *)(v46 + 16) == 0;
          ObjectAttributes.SecurityDescriptor = *(PVOID *)(v46 + 8);
          if ( !v42 )
            v29 = 66;
          ObjectAttributes.Attributes = v29;
        }
        inited = NtCreateFile(
                   &FileHandle,
                   DesiredAccess,
                   &ObjectAttributes,
                   &IoStatusBlock,
                   0,
                   0,
                   3u,
                   CreateDisposition,
                   CreateOptions,
                   EaBuffer,
                   v14 + 51);
        if ( inited >= 0 )
        {
          *a1 = FileHandle;
          FileHandle = 0;
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
    }
    else
    {
      inited = -1073741670;
    }
  }
  if ( FileHandle )
    CloseHandle(FileHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180002e90  push    rbp
0x180002e92  push    rbx
0x180002e93  push    rsi
0x180002e94  push    rdi
0x180002e95  push    r14
0x180002e97  push    r15
0x180002e99  lea     rbp, [rsp-228h]
0x180002ea1  sub     rsp, 328h
0x180002ea8  mov     rax, cs:__security_cookie
0x180002eaf  xor     rax, rsp
0x180002eb2  mov     [rbp+250h+var_40], rax
0x180002eb9  mov     r14, [rbp+250h+pszSrc]
0x180002ec0  xorps   xmm0, xmm0
0x180002ec3  mov     rsi, [rbp+250h+arg_50]
0x180002eca  mov     eax, edx
0x180002ecc  shr     eax, 10h
0x180002ecf  mov     ebx, edx
0x180002ed1  mov     [rsp+350h+var_2E8], eax
0x180002ed5  mov     r15, rcx
0x180002ed8  mov     rax, [rbp+250h+arg_40]
0x180002edf  lea     rcx, [rbp+250h+pszDest]; void *
0x180002ee3  mov     [rsp+350h+DesiredAccess], r8d
0x180002ee8  xorps   xmm1, xmm1
0x180002eeb  xor     edx, edx; Val
0x180002eed  mov     [rsp+350h+var_2E0], rax
0x180002ef2  mov     r8d, 240h; Size
0x180002ef8  mov     [rsp+350h+FileHandle], 0
0x180002f01  mov     edi, r9d
0x180002f04  movups  xmmword ptr [rsp+350h+ObjectAttributes.Length], xmm0
0x180002f09  movups  xmmword ptr [rbp+250h+ObjectAttributes.ObjectName], xmm0
0x180002f0d  movups  xmmword ptr [rbp+250h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002f11  movups  xmmword ptr [rbp+250h+DestinationString.Length], xmm0
0x180002f15  movups  xmmword ptr [rbp+250h+IoStatusBlock], xmm1
0x180002f19  call    memset_0
0x180002f1e  test    r15, r15
0x180002f21  jz      loc_1800032A4
0x180002f27  mov     [rsp+350h+arg_18], r12
0x180002f2f  mov     [rsp+350h+var_30], r13
0x180002f37  test    rsi, rsi
0x180002f3a  jnz     loc_1800032AE
0x180002f40  xor     r13d, r13d
0x180002f43  xor     r12d, r12d
0x180002f46  mov     qword ptr [r15], 0
0x180002f4d  test    edi, edi
0x180002f4f  jnz     loc_1800031C4
0x180002f55  mov     r11d, 7FFFFFFEh
0x180002f5b  lea     rdx, aDeviceHttpComm; "\\Device\\Http\\Communication"
0x180002f62  mov     r10d, 120h
0x180002f68  lea     r8, [rbp+250h+pszDest]
0x180002f6c  mov     ecx, r11d
0x180002f6f  mov     r9d, r10d
0x180002f72  test    rcx, rcx
0x180002f75  jz      short loc_180002F94
0x180002f77  movzx   eax, word ptr [rdx]
0x180002f7a  test    ax, ax
0x180002f7d  jz      short loc_180002F94
0x180002f7f  mov     [r8], ax
0x180002f83  add     rdx, 2
0x180002f87  add     r8, 2
0x180002f8b  dec     rcx
0x180002f8e  sub     r9, 1
0x180002f92  jnz     short loc_180002F72
0x180002f94  test    r9, r9
0x180002f97  lea     rcx, [r8-2]
0x180002f9b  cmovnz  rcx, r8
0x180002f9f  xor     eax, eax
0x180002fa1  mov     [rcx], ax
0x180002fa4  test    r14, r14
0x180002fa7  jz      loc_180003040
0x180002fad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002fb4  lea     rdx, [rbp+250h+pszDest]
0x180002fb8  mov     rcx, rax
0x180002fbb  nop     dword ptr [rax+rax+00h]
0x180002fc0  inc     rcx
0x180002fc3  cmp     word ptr [rdx+rcx*2], 0
0x180002fc8  jnz     short loc_180002FC0
0x180002fca  nop     word ptr [rax+rax+00h]
0x180002fd0  inc     rax
0x180002fd3  cmp     word ptr [r14+rax*2], 0
0x180002fd9  jnz     short loc_180002FD0
0x180002fdb  add     rax, 2
0x180002fdf  add     rax, rcx
0x180002fe2  cmp     rax, r10
0x180002fe5  jbe     loc_1800031A4
0x180002feb  mov     eax, 0C000000Dh
0x180002ff0  mov     r12, [rsp+350h+arg_18]
0x180002ff8  mov     r13, [rsp+350h+var_30]
0x180003000  mov     rcx, [rbp+250h+var_40]
0x180003007  xor     rcx, rsp; StackCookie
0x18000300a  call    __security_check_cookie
0x18000300f  add     rsp, 328h
0x180003016  pop     r15
0x180003018  pop     r14
0x18000301a  pop     rdi
0x18000301b  pop     rsi
0x18000301c  pop     rbx
0x18000301d  pop     rbp
0x18000301e  retn
0x18000301f  xor     eax, eax
0x180003021  mov     rcx, r10
0x180003024  sub     rcx, rdx
0x180003027  test    rdx, rdx
0x18000302a  cmovz   rcx, rax
0x18000302e  jnz     loc_180003258
0x180003034  mov     r8, r14; pszSrc
0x180003037  lea     rcx, [rbp+250h+pszDest]; pszDest
0x18000303b  call    StringCchCatW
0x180003040  lea     rdx, [rbp+250h+pszDest]; SourceString
0x180003044  lea     rcx, [rbp+250h+DestinationString]; DestinationString
0x180003048  call    cs:__imp_RtlInitUnicodeStringEx
0x18000304e  mov     edi, eax
0x180003050  test    eax, eax
0x180003052  js      loc_18000318F
0x180003058  mov     rcx, gs:60h
0x180003061  lea     r14d, [r13+33h]
0x180003065  mov     r8d, r14d; Size
0x180003068  xor     edx, edx; Flags
0x18000306a  mov     edi, r14d
0x18000306d  mov     rcx, [rcx+30h]; HeapHandle
0x180003071  call    cs:__imp_RtlAllocateHeap
0x180003077  mov     rsi, rax
0x18000307a  test    rax, rax
0x18000307d  jz      loc_1800032F3
0x180003083  mov     r8d, edi; Size
0x180003086  xor     edx, edx; Val
0x180003088  mov     rcx, rax; void *
0x18000308b  call    memset_0
0x180003090  mov     r8d, r13d; Size
0x180003093  mov     word ptr [rsi+4], 0F00h
0x180003099  lea     rax, [r8+18h]
0x18000309d  cmp     rax, 0FFFFh
0x1800030a3  jnb     loc_1800032FD
0x1800030a9  mov     dword ptr [rsi], 0
0x1800030af  lea     eax, [r13+18h]
0x1800030b3  mov     [rsi+6], ax
0x1800030b7  lea     rcx, [rsi+2Ch]; void *
0x1800030bb  movups  xmm0, xmmword ptr cs:aUlopenpacket00; "UlOpenPacket000"
0x1800030c2  mov     eax, [rsp+350h+var_2E8]
0x1800030c6  mov     rdx, r12; Src
0x1800030c9  movups  xmmword ptr [rsi+8], xmm0
0x1800030cd  mov     [rsi+1Ah], ax
0x1800030d1  mov     eax, [rbp+250h+arg_28]
0x1800030d7  mov     [rsi+1Ch], eax
0x1800030da  mov     [rsi+18h], bx
0x1800030de  mov     rax, cs:g_CommunicationChannel
0x1800030e5  mov     [rsi+20h], rax
0x1800030e9  mov     [rsi+28h], r13d
0x1800030ed  call    memcpy_0
0x1800030f2  mov     rdx, [rsp+350h+var_2E0]
0x1800030f7  lea     rax, [rbp+250h+DestinationString]
0x1800030fb  xor     ebx, ebx
0x1800030fd  mov     [rsp+350h+ObjectAttributes.Length], 30h ; '0'
0x180003105  mov     [rbp+250h+ObjectAttributes.RootDirectory], rbx
0x180003109  mov     ecx, 40h ; '@'
0x18000310e  mov     [rbp+250h+ObjectAttributes.Attributes], ecx
0x180003111  xorps   xmm0, xmm0
0x180003114  mov     [rbp+250h+ObjectAttributes.ObjectName], rax
0x180003118  movdqu  xmmword ptr [rbp+250h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000311d  test    rdx, rdx
0x180003120  jnz     loc_180003307
0x180003126  mov     eax, [rbp+250h+arg_38]
0x18000312c  lea     r9, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x180003130  mov     edx, [rsp+350h+DesiredAccess]; DesiredAccess
0x180003134  lea     r8, [rsp+350h+ObjectAttributes]; ObjectAttributes
0x180003139  mov     [rsp+350h+EaLength], r14d; EaLength
0x18000313e  lea     rcx, [rsp+350h+FileHandle]; FileHandle
0x180003143  mov     [rsp+350h+EaBuffer], rsi; EaBuffer
0x180003148  mov     [rsp+350h+CreateOptions], eax; CreateOptions
0x18000314c  mov     eax, [rbp+250h+arg_30]
0x180003152  mov     [rsp+350h+CreateDisposition], eax; CreateDisposition
0x180003156  mov     [rsp+350h+ShareAccess], 3; ShareAccess
0x18000315e  mov     [rsp+350h+FileAttributes], ebx; FileAttributes
0x180003162  mov     [rsp+350h+AllocationSize], rbx; AllocationSize
0x180003167  call    cs:__imp_NtCreateFile
0x18000316d  mov     edi, eax
0x18000316f  test    eax, eax
0x180003171  jns     loc_180003322
0x180003177  mov     rcx, gs:60h
0x180003180  mov     r8, rsi; P
0x180003183  xor     edx, edx; Flags
0x180003185  mov     rcx, [rcx+30h]; HeapHandle
0x180003189  call    cs:__imp_RtlFreeHeap
0x18000318f  mov     rcx, [rsp+350h+FileHandle]; hObject
0x180003194  test    rcx, rcx
0x180003197  jnz     loc_180003334
0x18000319d  mov     eax, edi
0x18000319f  jmp     loc_180002FF0
0x1800031a4  mov     rdx, r10; cchDest
0x1800031a7  lea     rax, [rbp+250h+pszDest]
0x1800031ab  cmp     word ptr [rax], 0
0x1800031af  jz      loc_18000301F
0x1800031b5  add     rax, 2
0x1800031b9  sub     rdx, 1
0x1800031bd  jnz     short loc_1800031AB
0x1800031bf  jmp     loc_18000301F
0x1800031c4  sub     edi, 1
0x1800031c7  jnz     loc_1800032C8
0x1800031cd  mov     r11d, 7FFFFFFEh
0x1800031d3  lea     r8, aDeviceHttpReqq; "\\Device\\Http\\ReqQueue"
0x1800031da  mov     r10d, 120h
0x1800031e0  lea     rax, [rbp+250h+pszDest]
0x1800031e4  mov     ecx, r11d
0x1800031e7  mov     edx, r10d
0x1800031ea  nop     word ptr [rax+rax+00h]
0x1800031f0  test    rcx, rcx
0x1800031f3  jz      short loc_180003248
0x1800031f5  movzx   r9d, word ptr [r8]
0x1800031f9  test    r9w, r9w
0x1800031fd  jz      short loc_180003248
0x1800031ff  mov     [rax], r9w
0x180003203  add     r8, 2
0x180003207  add     rax, 2
0x18000320b  dec     rcx
0x18000320e  sub     rdx, 1
0x180003212  jnz     short loc_1800031F0
0x180003214  test    rdx, rdx
0x180003217  lea     rcx, [rax-2]
0x18000321b  cmovnz  rcx, rax
0x18000321f  jmp     loc_180002F9F
0x180003224  test    rcx, rcx
0x180003227  jz      short loc_180003248
0x180003229  movzx   r9d, word ptr [r8]
0x18000322d  test    r9w, r9w
0x180003231  jz      short loc_180003248
0x180003233  mov     [rax], r9w
0x180003237  add     r8, 2
0x18000323b  add     rax, 2
0x18000323f  dec     rcx
0x180003242  sub     rdx, 1
0x180003246  jnz     short loc_180003224
0x180003248  test    rdx, rdx
0x18000324b  lea     rcx, [rax-2]
0x18000324f  cmovnz  rcx, rax
0x180003253  jmp     loc_180002F9F
0x180003258  lea     rax, [rbp+250h+pszDest]
0x18000325c  lea     rax, [rax+rcx*2]
0x180003260  lea     rdx, asc_18000E7BC; "\\"
0x180003267  sub     r10, rcx
0x18000326a  jz      short loc_180003271
0x18000326c  test    r11, r11
0x18000326f  jnz     short loc_180003286
0x180003271  test    r10, r10
0x180003274  lea     rcx, [rax-2]
0x180003278  cmovnz  rcx, rax
0x18000327c  xor     eax, eax
0x18000327e  mov     [rcx], ax
0x180003281  jmp     loc_180003034
0x180003286  movzx   ecx, word ptr [rdx]
0x180003289  test    cx, cx
0x18000328c  jz      short loc_180003271
0x18000328e  mov     [rax], cx
0x180003291  add     rdx, 2
0x180003295  add     rax, 2
0x180003299  dec     r11
0x18000329c  sub     r10, 1
0x1800032a0  jnz     short loc_18000326C
0x1800032a2  jmp     short loc_180003271
0x1800032a4  mov     eax, 0C000000Dh
0x1800032a9  jmp     loc_180003000
0x1800032ae  cmp     [rbp+250h+arg_48], 1
0x1800032b5  jnz     loc_180002FEB
0x1800032bb  mov     r13d, [rsi+4]
0x1800032bf  mov     r12, [rsi+8]
0x1800032c3  jmp     loc_180002F46
0x1800032c8  cmp     edi, 1
0x1800032cb  jnz     loc_180002FEB
0x1800032d1  mov     r11d, 7FFFFFFEh
0x1800032d7  lea     r8, aDeviceHttpClie; "\\Device\\Http\\ClientSession"
0x1800032de  mov     r10d, 120h
0x1800032e4  lea     rax, [rbp+250h+pszDest]
0x1800032e8  mov     ecx, r11d
0x1800032eb  mov     edx, r10d
0x1800032ee  jmp     loc_180003224
0x1800032f3  mov     edi, 0C000009Ah
0x1800032f8  jmp     loc_18000318F
0x1800032fd  mov     edi, 0C000000Dh
0x180003302  jmp     loc_180003177
0x180003307  mov     rax, [rdx+8]
0x18000330b  cmp     [rdx+10h], ebx
0x18000330e  mov     [rbp+250h+ObjectAttributes.SecurityDescriptor], rax
0x180003312  mov     eax, 42h ; 'B'
0x180003317  cmovnz  ecx, eax
0x18000331a  mov     [rbp+250h+ObjectAttributes.Attributes], ecx
0x18000331d  jmp     loc_180003126
0x180003322  mov     rax, [rsp+350h+FileHandle]
0x180003327  mov     [r15], rax
0x18000332a  mov     [rsp+350h+FileHandle], rbx
0x18000332f  jmp     loc_180003177
0x180003334  call    cs:__imp_CloseHandle
0x18000333a  jmp     loc_18000319D
```

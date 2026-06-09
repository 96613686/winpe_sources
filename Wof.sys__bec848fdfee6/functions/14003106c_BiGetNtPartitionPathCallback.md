# BiGetNtPartitionPathCallback

- ea: `0x14003106c`
- end: `0x14003137a`
- name: `BiGetNtPartitionPathCallback`
- size: `782`
- prototype: `char __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140032438`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14000db18`
- `0x140030d80`
- `0x14003106c`
- `0x140031520`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x140031197`
- `ntoskrnl!swprintf_s` at `0x1400312e9`
- `ntoskrnl!swprintf_s` at `0x140031197`
- `ntoskrnl!swprintf_s` at `0x1400312e9`
- `ntoskrnl!_wcsicmp` at `0x14003123b`
- `ntoskrnl!_wcsicmp` at `0x140031313`
- `ntoskrnl!_wcsicmp` at `0x14003123b`
- `ntoskrnl!_wcsicmp` at `0x140031313`

## pseudocode

```c
char __fastcall BiGetNtPartitionPathCallback(__int64 a1, unsigned int a2, __int64 a3)
{
  wchar_t *v3; // r14
  wchar_t *v4; // rsi
  __int64 v5; // rbx
  _DWORD *v6; // r13
  char v7; // di
  unsigned __int64 v8; // rcx
  _DWORD *v9; // r15
  wchar_t *v10; // rbx
  int v11; // r14d
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  _QWORD *v15; // rsi
  __int64 i; // rax
  __int64 v17; // r13
  int v18; // eax
  const wchar_t *PartitionVhdFilePath; // rax
  bool v20; // zf
  __int64 v21; // rcx
  __int64 ShareAccess; // [rsp+20h] [rbp-89h]
  PVOID P; // [rsp+30h] [rbp-79h] BYREF
  wchar_t *Dst; // [rsp+38h] [rbp-71h]
  void *FileHandle; // [rsp+40h] [rbp-69h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-61h]
  wchar_t *Str1; // [rsp+50h] [rbp-59h]
  _OWORD v28[2]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v29; // [rsp+78h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+17h] BYREF
  char v35; // [rsp+128h] [rbp+7Fh]

  v3 = *(wchar_t **)(a3 + 8);
  v4 = *(wchar_t **)(a3 + 16);
  v5 = *(_QWORD *)(a3 + 24);
  v6 = *(_DWORD **)(a3 + 40);
  v29 = 0;
  v7 = 0;
  FileHandle = 0;
  P = 0;
  v35 = *(_BYTE *)(a3 + 1);
  v26 = *(_QWORD **)(a3 + 32);
  memset(v28, 0, sizeof(v28));
  Str1 = v3;
  Dst = v4;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( (int)BiGetDriveLayoutBlock(a1, &P, v28) < 0 )
    return v7;
  if ( LODWORD(v28[0]) == 7 )
  {
    if ( *(_DWORD *)v5 != 7 )
      goto LABEL_8;
  }
  else if ( v3 )
  {
    goto LABEL_8;
  }
  v8 = *(_QWORD *)(v5 + 4) - *(_QWORD *)((char *)v28 + 4);
  if ( !v8 )
  {
    v8 = *(_QWORD *)(v5 + 12) - *(_QWORD *)((char *)v28 + 12);
    if ( !v8 )
      v8 = *(unsigned int *)(v5 + 20) - (unsigned __int64)DWORD1(v28[1]);
  }
  if ( v8 )
  {
    ExFreePoolWithTag_0(P, 0x4B444342u);
    return v7;
  }
LABEL_8:
  v9 = P;
  v10 = 0;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
      v11 = 0;
    else
      v11 = 2;
  }
  else
  {
    v11 = 1;
  }
  if ( !v6 )
  {
    if ( v11 == 1 )
    {
LABEL_35:
      v15 = 0;
      if ( !v11 )
      {
        if ( v6 )
        {
          v15 = v6;
        }
        else if ( v26 )
        {
          v15 = v26;
        }
      }
      for ( i = 0; ; i = (unsigned int)((_DWORD)P + 1) )
      {
        LODWORD(P) = i;
        if ( (unsigned int)i >= v9[1] )
          goto LABEL_22;
        v17 = 36 * i;
        v18 = v9[36 * i + 18];
        if ( v18 )
        {
          LODWORD(ShareAccess) = v18;
          swprintf_s(Dst, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, ShareAccess);
          if ( v35 )
          {
            PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(Dst);
            v10 = (wchar_t *)PartitionVhdFilePath;
            if ( PartitionVhdFilePath )
            {
              if ( !_wcsicmp(Str1, PartitionVhdFilePath) )
                goto LABEL_21;
              ExFreePoolWithTag_0(v10, 0x4B444342u);
              v10 = 0;
            }
          }
          if ( v11 == 1 )
          {
            if ( !v26 )
              continue;
            v20 = *v26 == *(_QWORD *)&v9[v17 + 14];
          }
          else
          {
            if ( !v15 )
              continue;
            v21 = *v15 - *(_QWORD *)&v9[v17 + 24];
            if ( *v15 == *(_QWORD *)&v9[v17 + 24] )
              v21 = v15[1] - *(_QWORD *)&v9[v17 + 26];
            v20 = v21 == 0;
          }
          if ( v20 )
            goto LABEL_21;
        }
      }
    }
LABEL_34:
    if ( v11 )
      goto LABEL_22;
    goto LABEL_35;
  }
  if ( v11 != 1 )
    goto LABEL_34;
  swprintf_s(v4, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, *v6);
  RtlInitUnicodeString_0(&DestinationString, v4);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile_0(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
  {
    ZwClose_0(FileHandle);
LABEL_21:
    v7 = 1;
  }
LABEL_22:
  ExFreePoolWithTag_0(v9, 0x4B444342u);
  v12 = Str1;
  if ( !Str1 || v35 || !v7 )
  {
LABEL_28:
    if ( !v10 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v13 = (const wchar_t *)BiGetPartitionVhdFilePath(Dst);
  v10 = (wchar_t *)v13;
  if ( !v13 || _wcsicmp(v12, v13) )
  {
    v7 = 0;
    goto LABEL_28;
  }
LABEL_29:
  ExFreePoolWithTag_0(v10, 0x4B444342u);
LABEL_30:
  if ( v7 )
    *(_BYTE *)a3 = 1;
  return v7;
}

```

## disassembly

```asm
0x14003106c  mov     [rsp-8+arg_10], r8
0x140031071  mov     [rsp-8+arg_8], edx
0x140031075  push    rbp
0x140031076  push    rbx
0x140031077  push    rsi
0x140031078  push    rdi
0x140031079  push    r13
0x14003107b  push    r14
0x14003107d  push    r15
0x14003107f  lea     rbp, [rsp-27h]
0x140031084  sub     rsp, 0D0h
0x14003108b  mov     r14, [r8+8]
0x14003108f  lea     rdx, [rbp+57h+P]
0x140031093  mov     rsi, [r8+10h]
0x140031097  xorps   xmm0, xmm0
0x14003109a  mov     rbx, [r8+18h]
0x14003109e  xor     eax, eax
0x1400310a0  mov     r13, [r8+28h]
0x1400310a4  xorps   xmm1, xmm1
0x1400310a7  mov     [rbp+57h+var_88], rax
0x1400310ab  xor     dil, dil
0x1400310ae  mov     [rbp+57h+FileHandle], rax
0x1400310b2  mov     [rbp+57h+P], rax
0x1400310b6  mov     al, [r8+1]
0x1400310ba  mov     [rbp+57h+arg_18], al
0x1400310bd  mov     rax, [r8+20h]
0x1400310c1  lea     r8, [rbp+57h+var_A8]
0x1400310c5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400310c9  mov     [rbp+57h+var_B8], rax
0x1400310cd  movups  [rbp+57h+var_A8], xmm0
0x1400310d1  mov     [rbp+57h+Str1], r14
0x1400310d5  movups  [rbp+57h+var_98], xmm0
0x1400310d9  mov     [rbp+57h+Dst], rsi
0x1400310dd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400310e1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400310e5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400310e9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1400310ed  call    BiGetDriveLayoutBlock
0x1400310f2  test    eax, eax
0x1400310f4  js      loc_14003126C
0x1400310fa  cmp     dword ptr [rbp+57h+var_A8], 7
0x1400310fe  jnz     short loc_140031145
0x140031100  cmp     dword ptr [rbx], 7
0x140031103  jnz     short loc_14003113F
0x140031105  mov     rcx, [rbx+4]
0x140031109  sub     rcx, qword ptr [rbp+57h+var_A8+4]
0x14003110d  jnz     short loc_140031122
0x14003110f  mov     rcx, [rbx+0Ch]
0x140031113  sub     rcx, qword ptr [rbp+57h+var_A8+0Ch]
0x140031117  jnz     short loc_140031122
0x140031119  mov     eax, dword ptr [rbp+57h+var_98+4]
0x14003111c  mov     ecx, [rbx+14h]
0x14003111f  sub     rcx, rax
0x140031122  test    rcx, rcx
0x140031125  jnz     short loc_14003114C
0x140031127  mov     r15, [rbp+57h+P]
0x14003112b  xor     ebx, ebx
0x14003112d  mov     ecx, [r15]
0x140031130  test    ecx, ecx
0x140031132  jz      short loc_140031164
0x140031134  cmp     ecx, 1
0x140031137  jz      short loc_14003115F
0x140031139  lea     r14d, [rbx+2]
0x14003113d  jmp     short loc_14003116A
0x14003113f  cmp     dword ptr [rbp+57h+var_A8], 7
0x140031143  jz      short loc_140031127
0x140031145  test    r14, r14
0x140031148  jnz     short loc_140031127
0x14003114a  jmp     short loc_140031105
0x14003114c  mov     rcx, [rbp+57h+P]; P
0x140031150  mov     edx, 4B444342h; Tag
0x140031155  call    ExFreePoolWithTag_0
0x14003115a  jmp     loc_14003126C
0x14003115f  xor     r14d, r14d
0x140031162  jmp     short loc_14003116A
0x140031164  mov     r14d, 1
0x14003116a  test    r13, r13
0x14003116d  jz      loc_140031282
0x140031173  cmp     r14d, 1
0x140031177  jnz     loc_140031288
0x14003117d  mov     eax, [r13+0]
0x140031181  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x140031188  mov     r9d, [rbp+57h+arg_8]
0x14003118c  lea     edx, [r14+34h]; SizeInWords
0x140031190  mov     rcx, rsi; Dst
0x140031193  mov     dword ptr [rsp+100h+ShareAccess], eax
0x140031197  call    cs:__imp_swprintf_s
0x14003119e  nop     dword ptr [rax+rax+00h]
0x1400311a3  mov     rdx, rsi; SourceString
0x1400311a6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400311aa  call    RtlInitUnicodeString_0
0x1400311af  lea     rax, [rbp+57h+DestinationString]
0x1400311b3  mov     [rsp+100h+OpenOptions], ebx; OpenOptions
0x1400311b7  xorps   xmm0, xmm0
0x1400311ba  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400311be  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400311c2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400311c9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400311cd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400311d1  mov     edx, 80000000h; DesiredAccess
0x1400311d6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400311dd  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400311e1  mov     dword ptr [rsp+100h+ShareAccess], 3; ShareAccess
0x1400311e9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400311ee  call    ZwOpenFile_0
0x1400311f3  test    eax, eax
0x1400311f5  js      short loc_140031203
0x1400311f7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400311fb  call    ZwClose_0
0x140031200  mov     dil, 1
0x140031203  mov     edx, 4B444342h; Tag
0x140031208  mov     rcx, r15; P
0x14003120b  call    ExFreePoolWithTag_0
0x140031210  mov     rsi, [rbp+57h+Str1]
0x140031214  test    rsi, rsi
0x140031217  jz      short loc_14003124E
0x140031219  cmp     [rbp+57h+arg_18], 0
0x14003121d  jnz     short loc_14003124E
0x14003121f  test    dil, dil
0x140031222  jz      short loc_14003124E
0x140031224  mov     rcx, [rbp+57h+Dst]; SourceString
0x140031228  call    BiGetPartitionVhdFilePath
0x14003122d  mov     rbx, rax
0x140031230  test    rax, rax
0x140031233  jz      short loc_14003124B
0x140031235  mov     rdx, rax; Str2
0x140031238  mov     rcx, rsi; Str1
0x14003123b  call    cs:__imp__wcsicmp
0x140031242  nop     dword ptr [rax+rax+00h]
0x140031247  test    eax, eax
0x140031249  jz      short loc_140031253
0x14003124b  xor     dil, dil
0x14003124e  test    rbx, rbx
0x140031251  jz      short loc_140031260
0x140031253  mov     edx, 4B444342h; Tag
0x140031258  mov     rcx, rbx; P
0x14003125b  call    ExFreePoolWithTag_0
0x140031260  test    dil, dil
0x140031263  jz      short loc_14003126C
0x140031265  mov     rax, [rbp+57h+arg_10]
0x140031269  mov     byte ptr [rax], 1
0x14003126c  mov     al, dil
0x14003126f  add     rsp, 0D0h
0x140031276  pop     r15
0x140031278  pop     r14
0x14003127a  pop     r13
0x14003127c  pop     rdi
0x14003127d  pop     rsi
0x14003127e  pop     rbx
0x14003127f  pop     rbp
0x140031280  retn
0x140031282  cmp     r14d, 1
0x140031286  jz      short loc_140031291
0x140031288  test    r14d, r14d
0x14003128b  jnz     loc_140031203
0x140031291  xor     esi, esi
0x140031293  test    r14d, r14d
0x140031296  jnz     short loc_1400312AD
0x140031298  test    r13, r13
0x14003129b  jz      short loc_1400312A2
0x14003129d  mov     rsi, r13
0x1400312a0  jmp     short loc_1400312AD
0x1400312a2  mov     rcx, [rbp+57h+var_B8]
0x1400312a6  test    rcx, rcx
0x1400312a9  cmovnz  rsi, rcx
0x1400312ad  xor     eax, eax
0x1400312af  mov     dword ptr [rbp+57h+P], eax
0x1400312b2  cmp     eax, [r15+4]
0x1400312b6  jnb     loc_140031203
0x1400312bc  lea     r13, [rax+rax*8]
0x1400312c0  shl     r13, 4
0x1400312c4  mov     eax, [r15+r13+48h]
0x1400312c9  test    eax, eax
0x1400312cb  jz      loc_140031370
0x1400312d1  mov     r9d, [rbp+57h+arg_8]
0x1400312d5  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x1400312dc  mov     rcx, [rbp+57h+Dst]; Dst
0x1400312e0  mov     edx, 35h ; '5'; SizeInWords
0x1400312e5  mov     dword ptr [rsp+100h+ShareAccess], eax
0x1400312e9  call    cs:__imp_swprintf_s
0x1400312f0  nop     dword ptr [rax+rax+00h]
0x1400312f5  cmp     [rbp+57h+arg_18], dil
0x1400312f9  jz      short loc_140031336
0x1400312fb  mov     rcx, [rbp+57h+Dst]; SourceString
0x1400312ff  call    BiGetPartitionVhdFilePath
0x140031304  mov     rbx, rax
0x140031307  test    rax, rax
0x14003130a  jz      short loc_140031336
0x14003130c  mov     rcx, [rbp+57h+Str1]; Str1
0x140031310  mov     rdx, rax; Str2
0x140031313  call    cs:__imp__wcsicmp
0x14003131a  nop     dword ptr [rax+rax+00h]
0x14003131f  test    eax, eax
0x140031321  jz      loc_140031200
0x140031327  mov     edx, 4B444342h; Tag
0x14003132c  mov     rcx, rbx; P
0x14003132f  call    ExFreePoolWithTag_0
0x140031334  xor     ebx, ebx
0x140031336  cmp     r14d, 1
0x14003133a  jnz     short loc_14003134F
0x14003133c  mov     rcx, [rbp+57h+var_B8]
0x140031340  test    rcx, rcx
0x140031343  jz      short loc_140031370
0x140031345  mov     rax, [r15+r13+38h]
0x14003134a  cmp     [rcx], rax
0x14003134d  jmp     short loc_14003136A
0x14003134f  test    rsi, rsi
0x140031352  jz      short loc_140031370
0x140031354  mov     rcx, [rsi]
0x140031357  sub     rcx, [r15+r13+60h]
0x14003135c  jnz     short loc_140031367
0x14003135e  mov     rcx, [rsi+8]
0x140031362  sub     rcx, [r15+r13+68h]
0x140031367  test    rcx, rcx
0x14003136a  jz      loc_140031200
0x140031370  mov     eax, dword ptr [rbp+57h+P]
0x140031373  inc     eax
0x140031375  jmp     loc_1400312AF
```

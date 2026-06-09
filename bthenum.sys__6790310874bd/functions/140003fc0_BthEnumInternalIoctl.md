# BthEnumInternalIoctl

- ea: `0x140003fc0`
- end: `0x14000422e`
- name: `BthEnumInternalIoctl`
- size: `622`
- prototype: `NTSTATUS __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003fc0`
- `0x140004234`
- `0x140004340`
- `0x140007e40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400040df`
- `ntoskrnl!IofCompleteRequest` at `0x1400040df`
- `ntoskrnl!IofCallDriver` at `0x140003ff7`
- `ntoskrnl!IofCallDriver` at `0x140004214`
- `ntoskrnl!IofCallDriver` at `0x140003ff7`
- `ntoskrnl!IofCallDriver` at `0x140004214`

## pseudocode

```c
NTSTATUS __fastcall BthEnumInternalIoctl(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  char v6; // si
  unsigned int Length; // r8d
  __int64 v8; // rbp
  __int64 v9; // rsi
  int v10; // edi
  _OWORD *UserBuffer; // rax
  _OWORD *v12; // rcx
  __int64 v13; // rdx
  __int128 v14; // xmm1
  _IO_SECURITY_CONTEXT *SecurityContext; // rax
  int FullCreateOptions_high; // r8d
  _IO_STACK_LOCATION *v17; // rax
  _IO_STACK_LOCATION *v18; // rax

  v2 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( *(_DWORD *)v2 == 542065734 )
  {
    ++a2->CurrentLocation;
    a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
    return IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 24), a2);
  }
  v6 = 0;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v8 = *(_QWORD *)(*(_QWORD *)(v2 + 8) + 64LL);
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 4259843 )
  {
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( SecurityContext )
    {
      FullCreateOptions_high = HIWORD(SecurityContext->FullCreateOptions);
      if ( FullCreateOptions_high == 258
        || HIWORD(SecurityContext->FullCreateOptions) == 259
        || HIWORD(SecurityContext->FullCreateOptions) == 514
        || HIWORD(SecurityContext->FullCreateOptions) == 515
        || HIWORD(SecurityContext->FullCreateOptions) == 528
        || HIWORD(SecurityContext->FullCreateOptions) == 529
        || (unsigned int)HIWORD(SecurityContext->FullCreateOptions) - 530 <= 1 )
      {
        if ( a2->CurrentLocation < *(_BYTE *)(a1 + 76) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_ddD(WPP_GLOBAL_Control->DeviceExtension, *(char *)(a1 + 76), FullCreateOptions_high, a1);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_Dddd(WPP_GLOBAL_Control->DeviceExtension, a2->StackCount, FullCreateOptions_high, a1);
          v17 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
          *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v17[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v17->Parameters.SetQuota + 6);
          v17[-1].FileObject = v17->FileObject;
          v17[-1].Control = 0;
          v6 = 1;
          v18 = a2->Tail.Overlay.CurrentStackLocation;
          v18[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))IoCompletionForOpenChannelSuccess;
          v18[-1].Context = (void *)v2;
          v18[-1].Control = -64;
        }
      }
    }
    goto LABEL_29;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 4259847 )
  {
    v9 = 1840;
    if ( Length < 0x730 )
      goto LABEL_7;
    memmove(a2->UserBuffer, (const void *)(v2 + 1040), 0x730u);
LABEL_13:
    v10 = 0;
    goto LABEL_14;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 4259851 )
  {
LABEL_29:
    if ( !v6 )
    {
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
    }
    return IofCallDriver(*(PDEVICE_OBJECT *)(v8 + 24), a2);
  }
  v9 = 272;
  if ( Length >= 0x110 )
  {
    UserBuffer = a2->UserBuffer;
    v12 = (_OWORD *)(v2 + 184);
    v13 = 2;
    do
    {
      *UserBuffer = *v12;
      UserBuffer[1] = v12[1];
      UserBuffer[2] = v12[2];
      UserBuffer[3] = v12[3];
      UserBuffer[4] = v12[4];
      UserBuffer[5] = v12[5];
      UserBuffer[6] = v12[6];
      v14 = v12[7];
      v12 += 8;
      UserBuffer[7] = v14;
      UserBuffer += 8;
      --v13;
    }
    while ( v13 );
    *UserBuffer = *v12;
    goto LABEL_13;
  }
LABEL_7:
  v9 = 0;
  v10 = -1073741306;
LABEL_14:
  a2->IoStatus.Information = v9;
  a2->IoStatus.Status = v10;
  IofCompleteRequest(a2, 0);
  return v10;
}

```

## disassembly

```asm
0x140003fc0  push    rbx
0x140003fc2  push    rbp
0x140003fc3  push    rsi
0x140003fc4  push    rdi
0x140003fc5  sub     rsp, 58h
0x140003fc9  mov     rdi, [rcx+40h]
0x140003fcd  mov     rbx, rdx
0x140003fd0  mov     rdx, [rdx+0B8h]
0x140003fd7  mov     r9, rcx
0x140003fda  cmp     dword ptr [rdi], 204F4446h
0x140003fe0  jnz     short loc_140004008
0x140003fe2  inc     byte ptr [rbx+43h]
0x140003fe5  lea     rax, [rdx+48h]
0x140003fe9  mov     [rbx+0B8h], rax
0x140003ff0  mov     rdx, rbx; Irp
0x140003ff3  mov     rcx, [rdi+18h]; DeviceObject
0x140003ff7  call    cs:__imp_IofCallDriver
0x140003ffe  nop     dword ptr [rax+rax+00h]
0x140004003  jmp     loc_140004224
0x140004008  mov     rax, [rdi+8]
0x14000400c  xor     sil, sil
0x14000400f  mov     ecx, [rdx+18h]
0x140004012  mov     r8d, [rdx+8]
0x140004016  mov     rbp, [rax+40h]
0x14000401a  sub     ecx, 410003h
0x140004020  jz      loc_1400040F0
0x140004026  sub     ecx, 4
0x140004029  jz      loc_1400040B4
0x14000402f  cmp     ecx, 4
0x140004032  jnz     loc_1400041FD
0x140004038  mov     esi, 110h
0x14000403d  cmp     r8d, esi
0x140004040  jnb     short loc_14000404E
0x140004042  xor     esi, esi
0x140004044  mov     edi, 0C0000206h
0x140004049  jmp     loc_1400040D3
0x14000404e  mov     rax, [rbx+70h]
0x140004052  lea     rcx, [rdi+0B8h]
0x140004059  mov     edx, 2
0x14000405e  lea     r8d, [rdx+7Eh]
0x140004062  movups  xmm0, xmmword ptr [rcx]
0x140004065  movups  xmmword ptr [rax], xmm0
0x140004068  movups  xmm1, xmmword ptr [rcx+10h]
0x14000406c  movups  xmmword ptr [rax+10h], xmm1
0x140004070  movups  xmm0, xmmword ptr [rcx+20h]
0x140004074  movups  xmmword ptr [rax+20h], xmm0
0x140004078  movups  xmm1, xmmword ptr [rcx+30h]
0x14000407c  movups  xmmword ptr [rax+30h], xmm1
0x140004080  movups  xmm0, xmmword ptr [rcx+40h]
0x140004084  movups  xmmword ptr [rax+40h], xmm0
0x140004088  movups  xmm1, xmmword ptr [rcx+50h]
0x14000408c  movups  xmmword ptr [rax+50h], xmm1
0x140004090  movups  xmm0, xmmword ptr [rcx+60h]
0x140004094  movups  xmmword ptr [rax+60h], xmm0
0x140004098  movups  xmm1, xmmword ptr [rcx+70h]
0x14000409c  add     rcx, r8
0x14000409f  movups  xmmword ptr [rax+70h], xmm1
0x1400040a3  add     rax, r8
0x1400040a6  sub     rdx, 1
0x1400040aa  jnz     short loc_140004062
0x1400040ac  movups  xmm0, xmmword ptr [rcx]
0x1400040af  movups  xmmword ptr [rax], xmm0
0x1400040b2  jmp     short loc_1400040D1
0x1400040b4  mov     esi, 730h
0x1400040b9  cmp     r8d, esi
0x1400040bc  jb      short loc_140004042
0x1400040be  mov     rcx, [rbx+70h]; void *
0x1400040c2  lea     rdx, [rdi+410h]; Src
0x1400040c9  mov     r8d, esi; Size
0x1400040cc  call    memmove
0x1400040d1  xor     edi, edi
0x1400040d3  xor     edx, edx; PriorityBoost
0x1400040d5  mov     [rbx+38h], rsi
0x1400040d9  mov     rcx, rbx; Irp
0x1400040dc  mov     [rbx+30h], edi
0x1400040df  call    cs:__imp_IofCompleteRequest
0x1400040e6  nop     dword ptr [rax+rax+00h]
0x1400040eb  jmp     loc_140004222
0x1400040f0  mov     rax, [rdx+8]
0x1400040f4  test    rax, rax
0x1400040f7  jz      loc_1400041FD
0x1400040fd  movzx   r8d, word ptr [rax+16h]
0x140004102  mov     ecx, r8d
0x140004105  sub     ecx, 102h
0x14000410b  jz      short loc_140004137
0x14000410d  sub     ecx, 1
0x140004110  jz      short loc_140004137
0x140004112  sub     ecx, 0FFh
0x140004118  jz      short loc_140004137
0x14000411a  sub     ecx, 1
0x14000411d  jz      short loc_140004137
0x14000411f  sub     ecx, 0Dh
0x140004122  jz      short loc_140004137
0x140004124  sub     ecx, 1
0x140004127  jz      short loc_140004137
0x140004129  sub     ecx, 1
0x14000412c  jz      short loc_140004137
0x14000412e  cmp     ecx, 1
0x140004131  jnz     loc_1400041FD
0x140004137  movsx   edx, byte ptr [r9+4Ch]
0x14000413c  movsx   ecx, byte ptr [rbx+43h]
0x140004140  cmp     cl, dl
0x140004142  jl      loc_1400041CA
0x140004148  lea     rax, WPP_RECORDER_INITIALIZED
0x14000414f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004156  jz      short loc_14000417F
0x140004158  mov     eax, edx
0x14000415a  movsx   edx, byte ptr [rbx+42h]
0x14000415e  mov     [rsp+78h+var_38], eax
0x140004162  mov     [rsp+78h+var_40], ecx
0x140004166  mov     rcx, cs:WPP_GLOBAL_Control
0x14000416d  mov     [rsp+78h+var_48], edx
0x140004171  mov     [rsp+78h+var_50], r8d
0x140004176  mov     rcx, [rcx+40h]
0x14000417a  call    WPP_RECORDER_SF_Dddd
0x14000417f  mov     rax, [rbx+0B8h]
0x140004186  lea     rcx, IoCompletionForOpenChannelSuccess
0x14000418d  movups  xmm0, xmmword ptr [rax]
0x140004190  movups  xmmword ptr [rax-48h], xmm0
0x140004194  movups  xmm1, xmmword ptr [rax+10h]
0x140004198  movups  xmmword ptr [rax-38h], xmm1
0x14000419c  movups  xmm0, xmmword ptr [rax+20h]
0x1400041a0  movups  xmmword ptr [rax-28h], xmm0
0x1400041a4  movsd   xmm1, qword ptr [rax+30h]
0x1400041a9  movsd   qword ptr [rax-18h], xmm1
0x1400041ae  mov     [rax-45h], sil
0x1400041b2  mov     sil, 1
0x1400041b5  mov     rax, [rbx+0B8h]
0x1400041bc  mov     [rax-10h], rcx
0x1400041c0  mov     [rax-8], rdi
0x1400041c4  mov     byte ptr [rax-45h], 0C0h
0x1400041c8  jmp     short loc_1400041FD
0x1400041ca  lea     rax, WPP_RECORDER_INITIALIZED
0x1400041d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400041d8  jz      short loc_1400041FD
0x1400041da  mov     eax, ecx
0x1400041dc  mov     [rsp+78h+var_40], r8d
0x1400041e1  movsx   ecx, byte ptr [rbx+42h]
0x1400041e5  mov     [rsp+78h+var_48], eax
0x1400041e9  mov     [rsp+78h+var_50], ecx
0x1400041ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041f4  mov     rcx, [rcx+40h]
0x1400041f8  call    WPP_RECORDER_SF_ddD
0x1400041fd  test    sil, sil
0x140004200  jnz     short loc_14000420D
0x140004202  inc     byte ptr [rbx+43h]
0x140004205  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000420d  mov     rcx, [rbp+18h]; DeviceObject
0x140004211  mov     rdx, rbx; Irp
0x140004214  call    cs:__imp_IofCallDriver
0x14000421b  nop     dword ptr [rax+rax+00h]
0x140004220  mov     edi, eax
0x140004222  mov     eax, edi
0x140004224  add     rsp, 58h
0x140004228  pop     rdi
0x140004229  pop     rsi
0x14000422a  pop     rbp
0x14000422b  pop     rbx
0x14000422c  retn
```

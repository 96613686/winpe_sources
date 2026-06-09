# FltpManualDeviceAttachWorker

- ea: `0x180077950`
- end: `0x180077c2a`
- name: `FltpManualDeviceAttachWorker`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180051250`

## callees

- `0x180009f20`
- `0x180014c10`
- `0x180024800`
- `0x180067920`
- `0x180077950`
- `0x180078740`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180077af5`
- `ntoskrnl!ObfDereferenceObject` at `0x180077b25`
- `ntoskrnl!ObfDereferenceObject` at `0x180077af5`
- `ntoskrnl!ObfDereferenceObject` at `0x180077b25`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180077ad9`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180077ad9`
- `ntoskrnl!ExDeleteTimer` at `0x180077bd0`
- `ntoskrnl!ExDeleteTimer` at `0x180077bd0`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180077a8d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180077a8d`
- `ntoskrnl!ExSetTimer` at `0x180077bb3`
- `ntoskrnl!ExSetTimer` at `0x180077bb3`

## pseudocode

```c
LONG_PTR __fastcall FltpManualDeviceAttachWorker(int a1)
{
  int v1; // esi
  char v2; // r15
  __int64 v3; // rbx
  char v4; // r14
  LONG_PTR result; // rax
  __int64 v6; // rbp
  unsigned __int64 v7; // r12
  unsigned int DeviceObjectPointer; // eax
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // rdi
  __int64 v10; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+30h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF

  v1 = a1;
  v2 = 0;
  FileObject = 0;
  DeviceObject = 0;
  v13 = 0;
  v3 = a1 & 1;
  if ( (a1 & 1) != 0 )
  {
    a1 = dword_18003EF6C;
    if ( dword_18003EF6C > 0 )
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
        McTemplateU0spdd_EtwWriteTransfer(
          dword_18003EF6C,
          (unsigned int)FrameSup_c1763,
          (unsigned int)"FltpManualDeviceAttachWorker",
          v1,
          dword_18003EF6C,
          dword_18003EF68);
      --dword_18003EF6C;
      v4 = 0;
LABEL_24:
      if ( dword_18003EF68 <= 0 || v4 )
      {
        result = ExDeleteTimer(qword_18003EF40, 0, 0, 0);
        qword_18003EF40 = 0;
      }
      else
      {
        if ( v2 )
        {
          v10 = (unsigned int)dword_18003EF70;
        }
        else
        {
          --dword_18003EF68;
          v10 = (unsigned int)qword_18003EF74;
        }
        *(_QWORD *)&v13 = 0;
        *((_QWORD *)&v13 + 1) = -1;
        result = ExSetTimer(qword_18003EF40, -10000000 * v10, 0, &v13);
      }
      goto LABEL_31;
    }
  }
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      a1,
      (unsigned int)FrameSup_c1779,
      (unsigned int)"FltpManualDeviceAttachWorker",
      v1,
      dword_18003EF6C,
      dword_18003EF68);
  result = (unsigned int)dword_18003ED90;
  if ( dword_18003ED90 )
  {
    v4 = 1;
    LODWORD(v6) = 0;
    if ( ManualDeviceAttachList[0] != -1 )
    {
      do
      {
        result = (unsigned int)v6;
        v7 = 24LL * (unsigned int)v6;
        if ( !ManualDeviceAttachList[v7 + 1] )
        {
          DeviceObjectPointer = IoGetDeviceObjectPointer(
                                  (PUNICODE_STRING)&a24[v7 / 2],
                                  0x80u,
                                  &FileObject,
                                  &DeviceObject);
          result = FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 1824, 0);
          if ( (int)result >= 0 )
          {
            if ( FltpFindFrameForDeviceStack(DeviceObject) )
            {
              DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
              FltpFsNotificationActual(DeviceAttachmentBaseRef);
              ObfDereferenceObject(DeviceAttachmentBaseRef);
              if ( ManualDeviceAttachList[v7] )
                ManualDeviceAttachList[v7 + 1] = 1;
              else
                v4 = 0;
              ManualDeviceAttachList[v7 + 2] = 0;
            }
            else
            {
              v4 = 0;
            }
            result = ObfDereferenceObject(FileObject);
          }
          else
          {
            v4 = 0;
            if ( ManualDeviceAttachList[v7 + 2] )
              v2 = 1;
          }
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( ManualDeviceAttachList[24 * v6] != -1 );
    }
  }
  else
  {
    v4 = 0;
  }
  if ( v3 )
    goto LABEL_24;
LABEL_31:
  if ( (v1 & 2) != 0 )
  {
    result = HIDWORD(qword_18003EF74);
    dword_18003EF6C = HIDWORD(qword_18003EF74);
  }
  return result;
}

```

## disassembly

```asm
0x180077950  mov     r11, rsp
0x180077953  sub     rsp, 88h
0x18007795a  mov     rax, cs:__security_cookie
0x180077961  xor     rax, rsp
0x180077964  mov     [rsp+88h+var_38], rax
0x180077969  mov     [r11+10h], rbx
0x18007796d  xorps   xmm0, xmm0
0x180077970  mov     [r11+20h], rsi
0x180077974  mov     rbx, rcx
0x180077977  mov     [r11-18h], r13
0x18007797b  mov     rsi, rcx
0x18007797e  xor     r13d, r13d
0x180077981  mov     [r11-20h], r14
0x180077985  mov     [r11-28h], r15
0x180077989  xor     r15b, r15b
0x18007798c  mov     [r11-50h], r13
0x180077990  mov     [r11-58h], r13
0x180077994  movups  [rsp+88h+var_48], xmm0
0x180077999  and     ebx, 1
0x18007799c  jz      short loc_1800779E3
0x18007799e  mov     ecx, cs:dword_18003EF6C
0x1800779a4  test    ecx, ecx
0x1800779a6  jle     short loc_1800779E3
0x1800779a8  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800779af  jz      short loc_1800779D5
0x1800779b1  mov     eax, cs:dword_18003EF68
0x1800779b7  lea     r8, aFltpmanualdevi; "FltpManualDeviceAttachWorker"
0x1800779be  mov     [rsp+88h+var_60], eax
0x1800779c2  lea     rdx, FrameSup_c1763
0x1800779c9  mov     r9, rsi
0x1800779cc  mov     [rsp+88h+var_68], ecx
0x1800779d0  call    McTemplateU0spdd_EtwWriteTransfer
0x1800779d5  dec     cs:dword_18003EF6C
0x1800779db  xor     r14b, r14b
0x1800779de  jmp     loc_180077B65
0x1800779e3  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800779ea  jz      short loc_180077A16
0x1800779ec  mov     eax, cs:dword_18003EF68
0x1800779f2  lea     r8, aFltpmanualdevi; "FltpManualDeviceAttachWorker"
0x1800779f9  mov     [rsp+88h+var_60], eax
0x1800779fd  lea     rdx, FrameSup_c1779
0x180077a04  mov     eax, cs:dword_18003EF6C
0x180077a0a  mov     r9, rsi
0x180077a0d  mov     [rsp+88h+var_68], eax
0x180077a11  call    McTemplateU0spdd_EtwWriteTransfer
0x180077a16  mov     eax, cs:dword_18003ED90
0x180077a1c  test    eax, eax
0x180077a1e  jnz     short loc_180077A28
0x180077a20  xor     r14b, r14b
0x180077a23  jmp     loc_180077B60
0x180077a28  cmp     cs:ManualDeviceAttachList, 0FFh
0x180077a2f  mov     r14b, 1
0x180077a32  mov     [rsp+88h+arg_10], rbp
0x180077a3a  mov     ebp, r13d
0x180077a3d  jz      loc_180077B58
0x180077a43  mov     [rsp+88h+var_8], rdi
0x180077a4b  mov     r13d, 720h
0x180077a51  mov     [rsp+88h+var_10], r12
0x180077a56  lea     rdi, ManualDeviceAttachList
0x180077a5d  mov     eax, ebp
0x180077a5f  lea     rcx, [rax+rax*2]
0x180077a63  lea     r12, ds:0[rcx*8]
0x180077a6b  cmp     byte ptr [r12+rdi+1], 0
0x180077a71  jnz     loc_180077B31
0x180077a77  lea     rcx, [rdi+8]
0x180077a7b  mov     edx, 80h; DesiredAccess
0x180077a80  add     rcx, r12; ObjectName
0x180077a83  lea     r9, [rsp+88h+DeviceObject]; DeviceObject
0x180077a88  lea     r8, [rsp+88h+FileObject]; FileObject
0x180077a8d  call    cs:__imp_IoGetDeviceObjectPointer
0x180077a94  nop     dword ptr [rax+rax+00h]
0x180077a99  xor     r9d, r9d
0x180077a9c  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x180077aa3  mov     ecx, eax
0x180077aa5  mov     r8d, r13d
0x180077aa8  call    FltpDbgStatus
0x180077aad  test    eax, eax
0x180077aaf  jns     short loc_180077AC0
0x180077ab1  xor     r14b, r14b
0x180077ab4  cmp     [r12+rdi+2], r14b
0x180077ab9  jz      short loc_180077B31
0x180077abb  mov     r15b, 1
0x180077abe  jmp     short loc_180077B31
0x180077ac0  mov     rcx, [rsp+88h+DeviceObject]; DeviceObject
0x180077ac5  call    FltpFindFrameForDeviceStack
0x180077aca  test    rax, rax
0x180077acd  jnz     short loc_180077AD4
0x180077acf  xor     r14b, r14b
0x180077ad2  jmp     short loc_180077B20
0x180077ad4  mov     rcx, [rsp+88h+DeviceObject]; DeviceObject
0x180077ad9  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180077ae0  nop     dword ptr [rax+rax+00h]
0x180077ae5  mov     rcx, rax; TargetDevice
0x180077ae8  mov     dl, 1
0x180077aea  mov     rdi, rax
0x180077aed  call    FltpFsNotificationActual
0x180077af2  mov     rcx, rdi; Object
0x180077af5  call    cs:__imp_ObfDereferenceObject
0x180077afc  nop     dword ptr [rax+rax+00h]
0x180077b01  lea     rdi, ManualDeviceAttachList
0x180077b08  cmp     byte ptr [r12+rdi], 0
0x180077b0d  jz      short loc_180077B17
0x180077b0f  mov     byte ptr [r12+rdi+1], 1
0x180077b15  jmp     short loc_180077B1A
0x180077b17  xor     r14b, r14b
0x180077b1a  mov     byte ptr [r12+rdi+2], 0
0x180077b20  mov     rcx, [rsp+88h+FileObject]; Object
0x180077b25  call    cs:__imp_ObfDereferenceObject
0x180077b2c  nop     dword ptr [rax+rax+00h]
0x180077b31  inc     ebp
0x180077b33  lea     rcx, ds:0[rbp*2]
0x180077b3b  add     rcx, rbp
0x180077b3e  cmp     byte ptr [rdi+rcx*8], 0FFh
0x180077b42  jnz     loc_180077A5D
0x180077b48  mov     r12, [rsp+88h+var_10]
0x180077b4d  xor     r13d, r13d
0x180077b50  mov     rdi, [rsp+88h+var_8]
0x180077b58  mov     rbp, [rsp+88h+arg_10]
0x180077b60  test    rbx, rbx
0x180077b63  jz      short loc_180077BE3
0x180077b65  mov     eax, cs:dword_18003EF68
0x180077b6b  test    eax, eax
0x180077b6d  jle     short loc_180077BC1
0x180077b6f  test    r14b, r14b
0x180077b72  jnz     short loc_180077BC1
0x180077b74  test    r15b, r15b
0x180077b77  jnz     short loc_180077B89
0x180077b79  dec     eax
0x180077b7b  mov     cs:dword_18003EF68, eax
0x180077b81  mov     eax, dword ptr cs:qword_18003EF74
0x180077b87  jmp     short loc_180077B8F
0x180077b89  mov     eax, cs:dword_18003EF70
0x180077b8f  mov     rcx, cs:qword_18003EF40
0x180077b96  lea     r9, [rsp+88h+var_48]
0x180077b9b  imul    rdx, rax, 0FFFFFFFFFF676980h
0x180077ba2  xor     r8d, r8d
0x180077ba5  mov     qword ptr [rsp+88h+var_48], r13
0x180077baa  mov     qword ptr [rsp+88h+var_48+8], 0FFFFFFFFFFFFFFFFh
0x180077bb3  call    cs:__imp_ExSetTimer
0x180077bba  nop     dword ptr [rax+rax+00h]
0x180077bbf  jmp     short loc_180077BE3
0x180077bc1  mov     rcx, cs:qword_18003EF40
0x180077bc8  xor     r9d, r9d
0x180077bcb  xor     r8d, r8d
0x180077bce  xor     edx, edx
0x180077bd0  call    cs:__imp_ExDeleteTimer
0x180077bd7  nop     dword ptr [rax+rax+00h]
0x180077bdc  mov     cs:qword_18003EF40, r13
0x180077be3  mov     r15, [rsp+88h+var_28]
0x180077be8  test    sil, 2
0x180077bec  mov     rsi, [rsp+88h+arg_18]
0x180077bf4  mov     r14, [rsp+88h+var_20]
0x180077bf9  mov     r13, [rsp+88h+var_18]
0x180077bfe  mov     rbx, [rsp+88h+arg_8]
0x180077c06  jz      short loc_180077C14
0x180077c08  mov     eax, dword ptr cs:qword_18003EF74+4
0x180077c0e  mov     cs:dword_18003EF6C, eax
0x180077c14  mov     rcx, [rsp+88h+var_38]
0x180077c19  xor     rcx, rsp; StackCookie
0x180077c1c  call    __security_check_cookie
0x180077c21  add     rsp, 88h
0x180077c28  retn
```

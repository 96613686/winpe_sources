# FltpFsControl

- ea: `0x18006ee20`
- end: `0x18006f150`
- name: `FltpFsControl`
- size: `816`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a40`
- `0x180003380`
- `0x180007500`
- `0x180009f20`
- `0x180060110`
- `0x18006c0c0`
- `0x18006ee20`
- `0x18006f160`
- `0x180070c80`
- `0x1800784c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18006eeeb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006eeeb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006ef13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006f0f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006ef13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006f0f9`
- `ntoskrnl!IofCompleteRequest` at `0x18006f026`
- `ntoskrnl!IofCompleteRequest` at `0x18006f04b`
- `ntoskrnl!IofCompleteRequest` at `0x18006f095`
- `ntoskrnl!IofCompleteRequest` at `0x18006f026`
- `ntoskrnl!IofCompleteRequest` at `0x18006f04b`
- `ntoskrnl!IofCompleteRequest` at `0x18006f095`

## pseudocode

```c
__int64 __fastcall FltpFsControl(PDEVICE_OBJECT DeviceObject, __int64 a2, __int64 a3, __int64 a4)
{
  __int128 Irp; // rax
  IRP *v5; // rdi
  __int64 v7; // rcx
  char v8; // al
  unsigned int v9; // esi
  int v11; // edx
  __int64 v12; // rbp
  int v13; // edx
  __int128 v14; // [rsp+20h] [rbp-38h] BYREF
  __m128i si128; // [rsp+30h] [rbp-28h]
  __int128 v16; // [rsp+40h] [rbp-18h]

  *((_QWORD *)&Irp + 1) = a2;
  v14 = 0;
  v5 = (IRP *)*((_QWORD *)&Irp + 1);
  si128 = 0;
  v16 = 0;
  if ( DeviceObject == ::DeviceObject )
  {
    *(_DWORD *)(*((_QWORD *)&Irp + 1) + 48LL) = -1073741808;
    *(_QWORD *)(*((_QWORD *)&Irp + 1) + 56LL) = 0;
    IofCompleteRequest(*((PIRP *)&Irp + 1), 0);
    return 3221225488LL;
  }
  else if ( DeviceObject == qword_18003EF38 )
  {
    return FltpMsgDispatch(DeviceObject, *((_QWORD *)&Irp + 1), a3, a4, v14, *((_QWORD *)&v14 + 1));
  }
  else
  {
    v7 = *(_QWORD *)(*((_QWORD *)&Irp + 1) + 184LL);
    v8 = *(_BYTE *)(v7 + 1);
    if ( v8 == 1 )
    {
      return FltpFsControlMountVolume((unsigned __int64)DeviceObject, *((IRP **)&Irp + 1));
    }
    else if ( v8 == 3 )
    {
      return FltpFsControlLoadFileSystem(DeviceObject, *((PIRP *)&Irp + 1));
    }
    else
    {
      *(_QWORD *)&Irp = DeviceObject->DeviceExtension;
      if ( (_QWORD)Irp && *(_WORD *)Irp == 0xF106 )
      {
        ++*(_BYTE *)(*((_QWORD *)&Irp + 1) + 67LL);
        *(_QWORD *)(*((_QWORD *)&Irp + 1) + 184LL) = v7 + 72;
        return FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), *((PIRP *)&Irp + 1));
      }
      *(_QWORD *)&Irp = *(_QWORD *)(Irp + 80);
      v14 = Irp;
      *(_QWORD *)&v16 = 0;
      DWORD2(v16) = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
      if ( (_QWORD)Irp )
      {
        if ( (*(_DWORD *)(Irp + 56) & 0x40) == 0 || !*(_DWORD *)(*(_QWORD *)(v14 + 104) + 192LL) )
        {
          if ( (_QWORD)v14 != *(_QWORD *)(v14 + 88)
            || *(_BYTE *)v7 != 13
            || (v13 = *(_DWORD *)(v7 + 24), v13 != 606820) && v13 != 623208
            || (LODWORD(v12) = FltpCopyOffloadCapable(*(_QWORD *)(v14 + 64)),
                (int)FltpDbgStatus((unsigned int)v12, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 6931, 0) >= 0) )
          {
            ++v5->CurrentLocation;
            ++v5->Tail.Overlay.CurrentStackLocation;
            return FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), v5);
          }
          v5->IoStatus.Information = 0;
          goto LABEL_26;
        }
        if ( *(_DWORD *)(v7 + 24) == 590920 )
        {
          v12 = (unsigned int)FltpProcessManageBypassIo(DeviceObject, *((_QWORD *)&Irp + 1), v14);
          if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 6953, 0) < 0 )
          {
            v5->IoStatus.Information = 0;
            if ( (_DWORD)v12 == -1073740590 )
            {
              v5->IoStatus.Information = 352;
              LODWORD(v12) = 0;
            }
LABEL_26:
            v5->IoStatus.Status = v12;
            IofCompleteRequest(v5, 0);
            return (unsigned int)v12;
          }
        }
        KeEnterCriticalRegion();
        v9 = FltpPassThrough((LARGE_INTEGER **)&v14);
        if ( (BYTE8(v16) & 4) != 0 )
        {
          if ( !v9 && *(_BYTE *)(si128.m128i_i64[0] + 12) == 13 )
          {
            v11 = *(_DWORD *)(*(_QWORD *)(si128.m128i_i64[0] + 248) + 40LL);
            if ( v11 == 606820 || v11 == 623208 )
            {
              v9 = FltpCopyOffloadCapable(*(_QWORD *)(v14 + 64));
              if ( (int)FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 7002, 0) < 0 )
                *(_DWORD *)(si128.m128i_i64[0] + 256) = v9;
            }
          }
          v9 = FltpLegacyProcessingAfterPreCallbacksCompleted(&v14, v9, 0);
        }
        else if ( (BYTE8(v16) & 8) != 0 )
        {
          KeLeaveCriticalRegion();
          ++v5->CurrentLocation;
          ++v5->Tail.Overlay.CurrentStackLocation;
          return (unsigned int)FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), v5);
        }
        KeLeaveCriticalRegion();
        return v9;
      }
      *(_DWORD *)(*((_QWORD *)&Irp + 1) + 48LL) = -1073741436;
      *(_QWORD *)(*((_QWORD *)&Irp + 1) + 56LL) = 0;
      IofCompleteRequest(*((PIRP *)&Irp + 1), 0);
      return 3221225860LL;
    }
  }
}

```

## disassembly

```asm
0x18006ee20  mov     [rsp+arg_8], rbx
0x18006ee25  mov     [rsp+arg_10], rsi
0x18006ee2a  push    rdi
0x18006ee2b  sub     rsp, 50h
0x18006ee2f  cmp     rcx, cs:DeviceObject
0x18006ee36  xorps   xmm0, xmm0
0x18006ee39  movups  [rsp+58h+var_38], xmm0
0x18006ee3e  mov     rdi, rdx
0x18006ee41  mov     rbx, rcx
0x18006ee44  movups  [rsp+58h+var_28], xmm0
0x18006ee49  movups  [rsp+58h+var_18], xmm0
0x18006ee4e  jz      loc_18006F039
0x18006ee54  cmp     rcx, cs:qword_18003EF38
0x18006ee5b  jz      loc_18006F061
0x18006ee61  mov     rcx, [rdx+0B8h]
0x18006ee68  movzx   eax, byte ptr [rcx+1]
0x18006ee6c  cmp     al, 1
0x18006ee6e  jz      loc_18006F06B
0x18006ee74  cmp     al, 3
0x18006ee76  jz      loc_18006F078
0x18006ee7c  mov     rax, [rbx+40h]
0x18006ee80  test    rax, rax
0x18006ee83  jnz     loc_18006EF7B
0x18006ee89  mov     rax, [rax+50h]
0x18006ee8d  xor     esi, esi
0x18006ee8f  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x18006ee97  mov     qword ptr [rsp+58h+var_38], rax
0x18006ee9c  mov     qword ptr [rsp+58h+var_38+8], rdi
0x18006eea1  mov     qword ptr [rsp+58h+var_18], rsi
0x18006eea6  mov     dword ptr [rsp+58h+var_18+8], esi
0x18006eeaa  movdqu  [rsp+58h+var_28], xmm0
0x18006eeb0  test    rax, rax
0x18006eeb3  jz      loc_18006F085
0x18006eeb9  mov     eax, [rax+38h]
0x18006eebc  mov     r8, qword ptr [rsp+58h+var_38]
0x18006eec1  mov     [rsp+58h+arg_0], rbp
0x18006eec6  test    al, 40h
0x18006eec8  jz      loc_18006EFB8
0x18006eece  mov     rax, [r8+68h]
0x18006eed2  cmp     [rax+0C0h], esi
0x18006eed8  jbe     loc_18006EFB8
0x18006eede  cmp     dword ptr [rcx+18h], 90448h
0x18006eee5  jz      loc_18006EFE2
0x18006eeeb  call    cs:__imp_KeEnterCriticalRegion
0x18006eef2  nop     dword ptr [rax+rax+00h]
0x18006eef7  lea     rcx, [rsp+58h+var_38]
0x18006eefc  call    FltpPassThrough
0x18006ef01  mov     esi, eax
0x18006ef03  mov     eax, dword ptr [rsp+58h+var_18+8]
0x18006ef07  test    al, 4
0x18006ef09  jnz     short loc_18006EF37
0x18006ef0b  test    al, 8
0x18006ef0d  jnz     loc_18006F0F9
0x18006ef13  call    cs:__imp_KeLeaveCriticalRegion
0x18006ef1a  nop     dword ptr [rax+rax+00h]
0x18006ef1f  mov     eax, esi
0x18006ef21  mov     rbp, [rsp+58h+arg_0]
0x18006ef26  mov     rbx, [rsp+58h+arg_8]
0x18006ef2b  mov     rsi, [rsp+58h+arg_10]
0x18006ef30  add     rsp, 50h
0x18006ef34  pop     rdi
0x18006ef35  retn
0x18006ef37  test    esi, esi
0x18006ef39  jnz     short loc_18006EF68
0x18006ef3b  mov     rcx, qword ptr [rsp+58h+var_28]
0x18006ef40  cmp     byte ptr [rcx+0Ch], 0Dh
0x18006ef44  jnz     short loc_18006EF68
0x18006ef46  mov     rcx, [rcx+0F8h]
0x18006ef4d  mov     edx, [rcx+28h]
0x18006ef50  cmp     edx, 94264h
0x18006ef56  jz      loc_18006F0BA
0x18006ef5c  cmp     edx, 98268h
0x18006ef62  jz      loc_18006F0BA
0x18006ef68  xor     r8d, r8d
0x18006ef6b  lea     rcx, [rsp+58h+var_38]
0x18006ef70  mov     edx, esi
0x18006ef72  call    FltpLegacyProcessingAfterPreCallbacksCompleted
0x18006ef77  mov     esi, eax
0x18006ef79  jmp     short loc_18006EF13
0x18006ef7b  mov     edx, 0F106h
0x18006ef80  cmp     [rax], dx
0x18006ef83  jnz     loc_18006EE89
0x18006ef89  inc     byte ptr [rdi+43h]
0x18006ef8c  lea     rax, [rcx+48h]
0x18006ef90  mov     [rdi+0B8h], rax
0x18006ef97  mov     rdx, rdi; Irp
0x18006ef9a  mov     rcx, [rbx+40h]
0x18006ef9e  mov     rcx, [rcx+8]; DeviceObject
0x18006efa2  call    FltpCallDriver
0x18006efa7  mov     rbx, [rsp+58h+arg_8]
0x18006efac  mov     rsi, [rsp+58h+arg_10]
0x18006efb1  add     rsp, 50h
0x18006efb5  pop     rdi
0x18006efb6  retn
0x18006efb8  cmp     r8, [r8+58h]
0x18006efbc  jz      loc_18006F127
0x18006efc2  inc     byte ptr [rdi+43h]
0x18006efc5  mov     rdx, rdi; Irp
0x18006efc8  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x18006efd0  mov     rcx, [rbx+40h]
0x18006efd4  mov     rcx, [rcx+8]; DeviceObject
0x18006efd8  call    FltpCallDriver
0x18006efdd  jmp     loc_18006EF21
0x18006efe2  mov     rdx, rdi
0x18006efe5  mov     rcx, rbx
0x18006efe8  call    FltpProcessManageBypassIo
0x18006efed  mov     r8d, 1B29h
0x18006eff3  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18006effa  xor     r9d, r9d
0x18006effd  mov     ecx, eax
0x18006efff  mov     ebp, eax
0x18006f001  call    FltpDbgStatus
0x18006f006  test    eax, eax
0x18006f008  jns     loc_18006EEEB
0x18006f00e  mov     [rdi+38h], rsi
0x18006f012  cmp     ebp, 0C00004D2h
0x18006f018  jz      loc_18006F0AB
0x18006f01e  xor     edx, edx; PriorityBoost
0x18006f020  mov     [rdi+30h], ebp
0x18006f023  mov     rcx, rdi; Irp
0x18006f026  call    cs:__imp_IofCompleteRequest
0x18006f02d  nop     dword ptr [rax+rax+00h]
0x18006f032  mov     eax, ebp
0x18006f034  jmp     loc_18006EF21
0x18006f039  xor     esi, esi
0x18006f03b  mov     dword ptr [rdx+30h], 0C0000010h
0x18006f042  mov     [rdx+38h], rsi
0x18006f046  mov     rcx, rdi; Irp
0x18006f049  xor     edx, edx; PriorityBoost
0x18006f04b  call    cs:__imp_IofCompleteRequest
0x18006f052  nop     dword ptr [rax+rax+00h]
0x18006f057  mov     eax, 0C0000010h
0x18006f05c  jmp     loc_18006EF26
0x18006f061  call    FltpMsgDispatch
0x18006f066  jmp     loc_18006EF26
0x18006f06b  mov     rcx, rbx
0x18006f06e  call    FltpFsControlMountVolume
0x18006f073  jmp     loc_18006EF26
0x18006f078  mov     rcx, rbx; DeviceObject
0x18006f07b  call    FltpFsControlLoadFileSystem
0x18006f080  jmp     loc_18006EF26
0x18006f085  xor     edx, edx; PriorityBoost
0x18006f087  mov     dword ptr [rdi+30h], 0C0000184h
0x18006f08e  mov     rcx, rdi; Irp
0x18006f091  mov     [rdi+38h], rsi
0x18006f095  call    cs:__imp_IofCompleteRequest
0x18006f09c  nop     dword ptr [rax+rax+00h]
0x18006f0a1  mov     eax, 0C0000184h
0x18006f0a6  jmp     loc_18006EF26
0x18006f0ab  mov     qword ptr [rdi+38h], 160h
0x18006f0b3  mov     ebp, esi
0x18006f0b5  jmp     loc_18006F01E
0x18006f0ba  mov     rcx, qword ptr [rsp+58h+var_38]
0x18006f0bf  mov     rcx, [rcx+40h]
0x18006f0c3  call    FltpCopyOffloadCapable
0x18006f0c8  mov     r8d, 1B5Ah
0x18006f0ce  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18006f0d5  xor     r9d, r9d
0x18006f0d8  mov     ecx, eax
0x18006f0da  mov     esi, eax
0x18006f0dc  call    FltpDbgStatus
0x18006f0e1  test    eax, eax
0x18006f0e3  jns     loc_18006EF68
0x18006f0e9  mov     rax, qword ptr [rsp+58h+var_28]
0x18006f0ee  mov     [rax+100h], esi
0x18006f0f4  jmp     loc_18006EF68
0x18006f0f9  call    cs:__imp_KeLeaveCriticalRegion
0x18006f100  nop     dword ptr [rax+rax+00h]
0x18006f105  inc     byte ptr [rdi+43h]
0x18006f108  mov     rdx, rdi; Irp
0x18006f10b  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x18006f113  mov     rcx, [rbx+40h]
0x18006f117  mov     rcx, [rcx+8]; DeviceObject
0x18006f11b  call    FltpCallDriver
0x18006f120  mov     esi, eax
0x18006f122  jmp     loc_18006EF1F
0x18006f127  cmp     byte ptr [rcx], 0Dh
0x18006f12a  jnz     loc_18006EFC2
0x18006f130  mov     edx, [rcx+18h]
0x18006f133  cmp     edx, 94264h
0x18006f139  jz      loc_18007AC40
0x18006f13f  cmp     edx, 98268h
0x18006f145  jnz     loc_18006EFC2
0x18006f14b  jmp     loc_18007AC40
0x18007ac40  mov     rcx, [r8+40h]
0x18007ac44  call    FltpCopyOffloadCapable
0x18007ac49  mov     r8d, 1B13h
0x18007ac4f  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18007ac56  xor     r9d, r9d
0x18007ac59  mov     ecx, eax
0x18007ac5b  mov     ebp, eax
0x18007ac5d  call    FltpDbgStatus
0x18007ac62  test    eax, eax
0x18007ac64  jns     loc_18006EFC2
0x18007ac6a  mov     [rdi+38h], rsi
0x18007ac6e  jmp     loc_18006F01E
```

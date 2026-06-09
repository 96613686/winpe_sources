# DisplayChildSiblings(_DeviceTreeData *,_LIST_ENTRY *,_TREEITEM *,int)

- ea: `0x180003a14`
- end: `0x180003c59`
- name: `?DisplayChildSiblings@@YAHPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@PEAU_TREEITEM@@H@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _DeviceTreeData *, struct _LIST_ENTRY *, struct _TREEITEM *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003a14`
- `0x180006514`

## callees

- `0x180003a14`
- `0x180006190`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x180003af1`
- `USER32!GetSystemMetrics` at `0x180003afe`
- `USER32!GetSystemMetrics` at `0x180003af1`
- `USER32!GetSystemMetrics` at `0x180003afe`
- `USER32!DestroyIcon` at `0x180003b48`
- `USER32!DestroyIcon` at `0x180003b48`
- `USER32!SendMessageW` at `0x180003bc9`
- `USER32!SendMessageW` at `0x180003c1e`
- `USER32!SendMessageW` at `0x180003bc9`
- `USER32!SendMessageW` at `0x180003c1e`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180003b37`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180003b37`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180003ab1`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180003ab1`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x180003b22`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x180003b22`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180003ae2`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180003ae2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180003b51`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180003b51`

## pseudocode

```c
__int64 __fastcall DisplayChildSiblings(
        struct _DeviceTreeData *a1,
        struct _LIST_ENTRY *a2,
        struct _TREEITEM *a3,
        int a4)
{
  unsigned int v8; // ebx
  struct _LIST_ENTRY *i; // rdi
  LRESULT v10; // rax
  HWND v11; // rdx
  HDEVINFO DeviceInfoList; // r14
  HWND v13; // r8
  UINT SystemMetrics; // ebx
  UINT v15; // eax
  int v16; // eax
  WCHAR *Blink; // rax
  int Blink_high; // eax
  struct _LIST_ENTRY *v19; // rdx
  struct _TREEITEM *v20; // r8
  LPARAM v21; // r9
  HICON hicon; // [rsp+30h] [rbp-79h] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-69h] BYREF
  int v25; // [rsp+50h] [rbp-59h]
  int v26; // [rsp+60h] [rbp-49h]
  int v27; // [rsp+64h] [rbp-45h]
  WCHAR *v28; // [rsp+68h] [rbp-41h]
  int v29; // [rsp+74h] [rbp-35h]
  int v30; // [rsp+78h] [rbp-31h]
  struct _LIST_ENTRY *v31; // [rsp+80h] [rbp-29h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+A0h] [rbp-9h] BYREF

  hicon = 0;
  v8 = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset_0(lParam, 0, 0x60u);
  for ( i = a2->Flink; i != a2; i = i->Flink )
  {
    if ( !*((_BYTE *)a1 + 97)
      || a4 && *((_BYTE *)a1 + 96)
      || !HIDWORD(i[10].Flink) && (unsigned int)IsHotPlugDevice((unsigned int)i[6].Flink) )
    {
      v11 = (HWND)*((_QWORD *)a1 + 2);
      v25 = 13;
      DeviceInfoList = SetupDiCreateDeviceInfoList(0, v11);
      if ( DeviceInfoList != (HDEVINFO)-1LL )
      {
        v13 = (HWND)*((_QWORD *)a1 + 2);
        DeviceInfoData.cbSize = 32;
        if ( SetupDiOpenDeviceInfoW(DeviceInfoList, (PCWSTR)i[2].Flink, v13, 0, &DeviceInfoData) )
        {
          SystemMetrics = GetSystemMetrics(50);
          v15 = GetSystemMetrics(49);
          if ( SetupDiLoadDeviceIcon(DeviceInfoList, &DeviceInfoData, v15, SystemMetrics, 0, &hicon) )
          {
            v16 = ImageList_ReplaceIcon(*((HIMAGELIST *)a1 + 11), -1, hicon);
            v25 |= 0x22u;
            v29 = v16;
            DestroyIcon(hicon);
          }
        }
        SetupDiDestroyDeviceInfoList(DeviceInfoList);
      }
      v30 = v29;
      lParam[0] = (LPARAM)a3;
      lParam[1] = -65534;
      Blink = (WCHAR *)i[2].Blink;
      if ( !Blink )
      {
        Blink = &szUnknown;
        if ( i[3].Flink )
          Blink = (WCHAR *)i[3].Flink;
      }
      v28 = Blink;
      v31 = i;
      v27 = 3840;
      Blink_high = HIDWORD(i[9].Blink);
      if ( Blink_high == 22 )
        v26 = 512;
      else
        v26 = Blink_high != 0 ? 0x100 : 0;
      v8 = 1;
      v10 = SendMessageW(*((HWND *)a1 + 1), 0x1132u, 0, (LPARAM)lParam);
    }
    else
    {
      v10 = 0;
    }
    v19 = i + 1;
    i[5].Blink = (struct _LIST_ENTRY *)v10;
    if ( v19->Flink != v19 )
    {
      v20 = a3;
      if ( *((_BYTE *)a1 + 96) )
        v20 = (struct _TREEITEM *)v10;
      if ( (unsigned int)DisplayChildSiblings(a1, v19, v20, v10 != 0) )
      {
        v21 = (LPARAM)i[5].Blink;
        v8 = 1;
        if ( v21 )
        {
          if ( *((_BYTE *)a1 + 96) )
            SendMessageW(*((HWND *)a1 + 1), 0x1102u, 2u, v21);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180003a14  mov     [rsp-8+arg_18], rbx
0x180003a19  push    rbp
0x180003a1a  push    rsi
0x180003a1b  push    rdi
0x180003a1c  push    r12
0x180003a1e  push    r13
0x180003a20  push    r14
0x180003a22  push    r15
0x180003a24  lea     rbp, [rsp-27h]
0x180003a29  sub     rsp, 0D0h
0x180003a30  mov     rax, cs:__security_cookie
0x180003a37  xor     rax, rsp
0x180003a3a  mov     [rbp+57h+var_40], rax
0x180003a3e  xor     r14d, r14d
0x180003a41  xorps   xmm0, xmm0
0x180003a44  mov     r12, r8
0x180003a47  mov     [rbp+57h+hicon], r14
0x180003a4b  mov     r15, rdx
0x180003a4e  mov     rsi, rcx
0x180003a51  xor     edx, edx; Val
0x180003a53  lea     rcx, [rbp+57h+lParam]; void *
0x180003a57  lea     r8d, [r14+60h]; Size
0x180003a5b  mov     r13d, r9d
0x180003a5e  mov     ebx, r14d
0x180003a61  movups  xmmword ptr [rbp+57h+var_60.cbSize], xmm0
0x180003a65  movups  xmmword ptr [rbp+57h+var_60.ClassGuid.Data4+4], xmm0
0x180003a69  call    memset_0
0x180003a6e  mov     rdi, [r15]
0x180003a71  jmp     loc_180003C27
0x180003a76  cmp     [rsi+61h], r14b
0x180003a7a  jz      short loc_180003AA4
0x180003a7c  test    r13d, r13d
0x180003a7f  jz      short loc_180003A87
0x180003a81  cmp     [rsi+60h], r14b
0x180003a85  jnz     short loc_180003AA4
0x180003a87  cmp     [rdi+0A4h], r14d
0x180003a8e  jnz     short loc_180003A9C
0x180003a90  mov     ecx, [rdi+60h]; unsigned int
0x180003a93  call    ?IsHotPlugDevice@@YAHK@Z; IsHotPlugDevice(ulong)
0x180003a98  test    eax, eax
0x180003a9a  jnz     short loc_180003AA4
0x180003a9c  mov     rax, r14
0x180003a9f  jmp     loc_180003BCF
0x180003aa4  mov     rdx, [rsi+10h]; hwndParent
0x180003aa8  xor     ecx, ecx; ClassGuid
0x180003aaa  mov     [rbp+57h+var_B0], 0Dh
0x180003ab1  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180003ab7  mov     r14, rax
0x180003aba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003abe  jz      loc_180003B57
0x180003ac4  mov     r8, [rsi+10h]; hwndParent
0x180003ac8  lea     rax, [rbp+57h+var_60]
0x180003acc  mov     [rbp+57h+var_60.cbSize], 20h ; ' '
0x180003ad3  xor     r9d, r9d; OpenFlags
0x180003ad6  mov     rdx, [rdi+20h]; DeviceInstanceId
0x180003ada  mov     rcx, r14; DeviceInfoSet
0x180003add  mov     [rsp+100h+DeviceInfoData], rax; DeviceInfoData
0x180003ae2  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180003ae8  test    eax, eax
0x180003aea  jz      short loc_180003B4E
0x180003aec  mov     ecx, 32h ; '2'; nIndex
0x180003af1  call    cs:__imp_GetSystemMetrics
0x180003af7  mov     ecx, 31h ; '1'; nIndex
0x180003afc  mov     ebx, eax
0x180003afe  call    cs:__imp_GetSystemMetrics
0x180003b04  lea     rcx, [rbp+57h+hicon]
0x180003b08  mov     r9d, ebx; cyIcon
0x180003b0b  mov     [rsp+100h+hIcon], rcx; hIcon
0x180003b10  lea     rdx, [rbp+57h+var_60]; DeviceInfoData
0x180003b14  mov     rcx, r14; DeviceInfoSet
0x180003b17  mov     dword ptr [rsp+100h+DeviceInfoData], 0; Flags
0x180003b1f  mov     r8d, eax; cxIcon
0x180003b22  call    cs:__imp_SetupDiLoadDeviceIcon
0x180003b28  test    eax, eax
0x180003b2a  jz      short loc_180003B4E
0x180003b2c  mov     r8, [rbp+57h+hicon]; hicon
0x180003b30  or      edx, 0FFFFFFFFh; i
0x180003b33  mov     rcx, [rsi+58h]; himl
0x180003b37  call    cs:__imp_ImageList_ReplaceIcon
0x180003b3d  mov     rcx, [rbp+57h+hicon]; hIcon
0x180003b41  or      [rbp+57h+var_B0], 22h
0x180003b45  mov     [rbp+57h+var_8C], eax
0x180003b48  call    cs:__imp_DestroyIcon
0x180003b4e  mov     rcx, r14; DeviceInfoSet
0x180003b51  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180003b57  mov     eax, [rbp+57h+var_8C]
0x180003b5a  xor     r14d, r14d
0x180003b5d  mov     [rbp+57h+var_88], eax
0x180003b60  mov     [rbp+57h+lParam], r12
0x180003b64  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFF0002h
0x180003b6c  mov     rax, [rdi+28h]
0x180003b70  test    rax, rax
0x180003b73  jnz     short loc_180003B85
0x180003b75  cmp     [rdi+30h], r14
0x180003b79  lea     rax, ?szUnknown@@3PAGA; ushort near * szUnknown
0x180003b80  cmovnz  rax, [rdi+30h]
0x180003b85  mov     [rbp+57h+var_98], rax
0x180003b89  mov     [rbp+57h+var_80], rdi
0x180003b8d  mov     [rbp+57h+var_9C], 0F00h
0x180003b94  mov     eax, [rdi+9Ch]
0x180003b9a  cmp     eax, 16h
0x180003b9d  jnz     short loc_180003BA8
0x180003b9f  mov     [rbp+57h+var_A0], 200h
0x180003ba6  jmp     short loc_180003BB4
0x180003ba8  neg     eax
0x180003baa  sbb     eax, eax
0x180003bac  and     eax, 100h
0x180003bb1  mov     [rbp+57h+var_A0], eax
0x180003bb4  mov     rcx, [rsi+8]; hWnd
0x180003bb8  lea     r9, [rbp+57h+lParam]; lParam
0x180003bbc  xor     r8d, r8d; wParam
0x180003bbf  mov     edx, 1132h; Msg
0x180003bc4  mov     ebx, 1
0x180003bc9  call    cs:__imp_SendMessageW
0x180003bcf  lea     rdx, [rdi+10h]; struct _LIST_ENTRY *
0x180003bd3  mov     [rdi+58h], rax
0x180003bd7  cmp     [rdx], rdx
0x180003bda  jz      short loc_180003C24
0x180003bdc  test    rax, rax
0x180003bdf  mov     r9d, r14d
0x180003be2  mov     r8, r12
0x180003be5  mov     rcx, rsi; struct _DeviceTreeData *
0x180003be8  setnz   r9b; int
0x180003bec  cmp     [rsi+60h], r14b
0x180003bf0  cmovnz  r8, rax; struct _TREEITEM *
0x180003bf4  call    ?DisplayChildSiblings@@YAHPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@PEAU_TREEITEM@@H@Z; DisplayChildSiblings(_DeviceTreeData *,_LIST_ENTRY *,_TREEITEM *,int)
0x180003bf9  test    eax, eax
0x180003bfb  jz      short loc_180003C24
0x180003bfd  mov     r9, [rdi+58h]; lParam
0x180003c01  mov     ebx, 1
0x180003c06  test    r9, r9
0x180003c09  jz      short loc_180003C24
0x180003c0b  cmp     [rsi+60h], r14b
0x180003c0f  jz      short loc_180003C24
0x180003c11  mov     rcx, [rsi+8]; hWnd
0x180003c15  lea     r8d, [rbx+1]; wParam
0x180003c19  mov     edx, 1102h; Msg
0x180003c1e  call    cs:__imp_SendMessageW
0x180003c24  mov     rdi, [rdi]
0x180003c27  cmp     rdi, r15
0x180003c2a  jnz     loc_180003A76
0x180003c30  mov     eax, ebx
0x180003c32  mov     rcx, [rbp+57h+var_40]
0x180003c36  xor     rcx, rsp; StackCookie
0x180003c39  call    __security_check_cookie
0x180003c3e  mov     rbx, [rsp+100h+arg_18]
0x180003c46  add     rsp, 0D0h
0x180003c4d  pop     r15
0x180003c4f  pop     r14
0x180003c51  pop     r13
0x180003c53  pop     r12
0x180003c55  pop     rdi
0x180003c56  pop     rsi
0x180003c57  pop     rbp
0x180003c58  retn
```

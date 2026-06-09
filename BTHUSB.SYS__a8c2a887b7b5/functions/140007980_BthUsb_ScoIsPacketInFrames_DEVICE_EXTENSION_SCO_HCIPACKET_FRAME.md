# BthUsb_ScoIsPacketInFrames(_DEVICE_EXTENSION *,_SCO_HCIPACKET_FRAME *)

- ea: `0x140007980`
- end: `0x140007b05`
- name: `?BthUsb_ScoIsPacketInFrames@@YAEPEAU_DEVICE_EXTENSION@@PEAU_SCO_HCIPACKET_FRAME@@@Z`
- size: `389`
- prototype: `unsigned __int8 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_HCIPACKET_FRAME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400085b4`

## callees

- `0x14000175c`
- `0x140007980`

## pseudocode

```c
bool __fastcall BthUsb_ScoIsPacketInFrames(struct _DEVICE_EXTENSION *a1, struct _SCO_HCIPACKET_FRAME *a2)
{
  char *v2; // r8
  unsigned int v3; // r9d
  int v5; // edx
  char v6; // bl
  unsigned int v8; // r10d
  unsigned int FRAMES_X_HCIPACKET; // eax
  int v10; // ecx
  unsigned int v11; // eax
  unsigned __int16 v12; // r8
  _SCO_USB_CHANNEL *v13; // rax

  v2 = (char *)a2 + 16;
  v3 = *((_DWORD *)a2 + 2);
  v5 = 1;
  v6 = 0;
  v8 = 1;
  FRAMES_X_HCIPACKET = a1->Sco.UsbAltSetting->FRAMES_X_HCIPACKET;
  if ( FRAMES_X_HCIPACKET <= 1 )
  {
LABEL_5:
    v11 = v3 * FRAMES_X_HCIPACKET;
    if ( v11 >= 3 )
    {
      if ( v3 >= 3 )
      {
        if ( v11 - 3 == *(unsigned __int8 *)(*(_QWORD *)a2 + 2LL) )
        {
          v12 = 0;
          while ( 1 )
          {
            v13 = &a1->Sco.Channel[v12];
            if ( v13->ConnectionHandle == (**(_WORD **)a2 & 0xFFF) )
              break;
            if ( ++v12 >= 3u )
              return v6;
          }
          return v13 != 0;
        }
        else
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            LOBYTE(v5) = 0;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v5,
            (_DWORD)v2,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            5,
            36,
            (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
        }
      }
      else
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          LOBYTE(v5) = 0;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          (_DWORD)v2,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          35,
          (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
      }
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        LOBYTE(v5) = 0;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        (_DWORD)v2,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        34,
        (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
    }
  }
  else
  {
    while ( 1 )
    {
      v10 = *((_DWORD *)v2 + 2);
      if ( !v10 || v3 != v10 )
        break;
      ++v8;
      v2 += 16;
      if ( v8 >= FRAMES_X_HCIPACKET )
        goto LABEL_5;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      LOBYTE(v5) = 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      (_DWORD)v2,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      33,
      (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x140007980  mov     [rsp+arg_0], rbx
0x140007985  push    rdi
0x140007986  sub     rsp, 40h
0x14000798a  mov     rax, [rcx+478h]
0x140007991  lea     r8, [rdx+10h]
0x140007995  mov     r9d, [rdx+8]
0x140007999  mov     r11, rdx
0x14000799c  mov     edx, 1
0x1400079a1  xor     bl, bl
0x1400079a3  mov     rdi, rcx
0x1400079a6  mov     r10d, edx
0x1400079a9  mov     eax, [rax+0Ch]
0x1400079ac  cmp     eax, edx
0x1400079ae  jbe     short loc_1400079C9
0x1400079b0  mov     ecx, [r8+8]
0x1400079b4  test    ecx, ecx
0x1400079b6  jz      short loc_140007A03
0x1400079b8  cmp     r9d, ecx
0x1400079bb  jnz     short loc_140007A03
0x1400079bd  add     r10d, edx
0x1400079c0  add     r8, 10h
0x1400079c4  cmp     r10d, eax
0x1400079c7  jb      short loc_1400079B0
0x1400079c9  imul    eax, r9d
0x1400079cd  mov     r10d, 3
0x1400079d3  cmp     eax, r10d
0x1400079d6  jnb     short loc_140007A4B
0x1400079d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079df  mov     eax, [rcx+2Ch]
0x1400079e2  test    al, 10h
0x1400079e4  jz      short loc_1400079EC
0x1400079e6  cmp     byte ptr [rcx+29h], 4
0x1400079ea  jnb     short loc_1400079EE
0x1400079ec  xor     dl, dl
0x1400079ee  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x1400079f5  mov     [rsp+48h+var_10], rax
0x1400079fa  mov     [rsp+48h+var_18], 22h ; '"'
0x140007a01  jmp     short loc_140007A2C
0x140007a03  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a0a  mov     eax, [rcx+2Ch]
0x140007a0d  test    al, 10h
0x140007a0f  jz      short loc_140007A17
0x140007a11  cmp     byte ptr [rcx+29h], 4
0x140007a15  jnb     short loc_140007A19
0x140007a17  xor     dl, dl
0x140007a19  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007a20  mov     [rsp+48h+var_10], rax
0x140007a25  mov     [rsp+48h+var_18], 21h ; '!'
0x140007a2c  mov     r9, [rcx+40h]
0x140007a30  mov     rcx, [rcx+18h]
0x140007a34  mov     [rsp+48h+var_20], 5
0x140007a3c  mov     [rsp+48h+var_28], 4
0x140007a41  call    WPP_RECORDER_AND_TRACE_SF_
0x140007a46  jmp     loc_140007AF7
0x140007a4b  cmp     r9d, r10d
0x140007a4e  jnb     short loc_140007A7B
0x140007a50  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a57  mov     eax, [rcx+2Ch]
0x140007a5a  test    al, 10h
0x140007a5c  jz      short loc_140007A64
0x140007a5e  cmp     byte ptr [rcx+29h], 4
0x140007a62  jnb     short loc_140007A66
0x140007a64  xor     dl, dl
0x140007a66  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007a6d  mov     [rsp+48h+var_10], rax
0x140007a72  mov     [rsp+48h+var_18], 23h ; '#'
0x140007a79  jmp     short loc_140007A2C
0x140007a7b  mov     r9, [r11]
0x140007a7e  add     eax, 0FFFFFFFDh
0x140007a81  movzx   ecx, byte ptr [r9+2]
0x140007a86  cmp     eax, ecx
0x140007a88  jz      short loc_140007AB8
0x140007a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a91  mov     eax, [rcx+2Ch]
0x140007a94  test    al, 10h
0x140007a96  jz      short loc_140007A9E
0x140007a98  cmp     byte ptr [rcx+29h], 4
0x140007a9c  jnb     short loc_140007AA0
0x140007a9e  xor     dl, dl
0x140007aa0  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007aa7  mov     [rsp+48h+var_10], rax
0x140007aac  mov     [rsp+48h+var_18], 24h ; '$'
0x140007ab3  jmp     loc_140007A2C
0x140007ab8  movzx   r9d, word ptr [r9]
0x140007abc  mov     eax, 0FFFh
0x140007ac1  and     r9w, ax
0x140007ac5  xor     r8d, r8d
0x140007ac8  movzx   eax, r8w
0x140007acc  imul    rax, 98h
0x140007ad3  add     rax, 2B0h
0x140007ad9  add     rax, rdi
0x140007adc  cmp     [rax], r9w
0x140007ae0  jz      short loc_140007AEE
0x140007ae2  add     r8w, dx
0x140007ae6  cmp     r8w, r10w
0x140007aea  jb      short loc_140007AC8
0x140007aec  jmp     short loc_140007AF7
0x140007aee  test    rax, rax
0x140007af1  movzx   ebx, bl
0x140007af4  cmovnz  ebx, edx
0x140007af7  mov     al, bl
0x140007af9  mov     rbx, [rsp+48h+arg_0]
0x140007afe  add     rsp, 40h
0x140007b02  pop     rdi
0x140007b03  retn
```

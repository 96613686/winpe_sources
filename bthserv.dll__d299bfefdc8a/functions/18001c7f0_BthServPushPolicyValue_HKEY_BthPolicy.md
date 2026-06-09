# BthServPushPolicyValue(HKEY__ *,BthPolicy)

- ea: `0x18001c7f0`
- end: `0x18001c98b`
- name: `?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z`
- size: `411`
- prototype: `LSTATUS __fastcall(HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001c994`

## callees

- `0x18001c7f0`
- `0x18001cff4`
- `0x180030264`
- `0x180030328`
- `0x1800304c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c905`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c905`

## pseudocode

```c
LSTATUS __fastcall BthServPushPolicyValue(HKEY a1, unsigned int a2)
{
  int PolicyValue; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // bl
  int v9; // eax
  bool v10; // r11
  __int64 v11; // r10
  char v12; // r11
  int v13; // edx
  int v14; // r8d
  const WCHAR *PolicyKeyValueName; // rax
  LSTATUS result; // eax
  signed int v17; // r8d
  __int64 v18; // r10
  int v19; // edx
  char v20; // r11
  int v21; // r8d
  int Data; // [rsp+90h] [rbp+18h] BYREF

  Data = 0;
  PolicyValue = BthGetPolicyValue(a2, &Data);
  v7 = (unsigned int)PolicyValue;
  v8 = 1;
  if ( PolicyValue >= 0 )
    goto LABEL_22;
  v5 = a2 - 1;
  if ( a2 == 1 )
  {
    v9 = 2;
    goto LABEL_15;
  }
  v5 = a2 - 2;
  if ( a2 == 2 )
    goto LABEL_13;
  v5 = a2 - 4;
  if ( a2 == 4 )
    goto LABEL_13;
  v5 = a2 - 8;
  if ( a2 == 8 )
    goto LABEL_13;
  v5 = a2 - 16;
  if ( a2 == 16 )
    goto LABEL_13;
  v5 = a2 - 32;
  if ( a2 == 32 )
    goto LABEL_12;
  v5 = a2 - 64;
  if ( a2 == 64 )
    goto LABEL_12;
  v5 = a2 - 1024;
  if ( a2 == 1024 )
  {
LABEL_13:
    v9 = 1;
    goto LABEL_15;
  }
  if ( a2 == 2048 )
  {
LABEL_12:
    v9 = 0;
    goto LABEL_15;
  }
  v9 = -1;
LABEL_15:
  Data = v9;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    BthGetPolicyName(a2);
    LOBYTE(v13) = v12;
    WPP_RECORDER_AND_TRACE_SF_sSD(*(_QWORD *)(v11 + 16), v13, v14, *(_QWORD *)(v11 + 40));
  }
LABEL_22:
  PolicyKeyValueName = (const WCHAR *)BthGetPolicyKeyValueName(a2, v5, v6, v7);
  result = RegSetKeyValueW(a1, 0, PolicyKeyValueName, 4u, &Data, 4u);
  v17 = result;
  if ( result > 0 )
    v17 = (unsigned __int16)result | 0x80070000;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v8 = 0;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      BthGetPolicyName(a2);
      LOBYTE(v19) = v8;
      LOBYTE(v21) = v20;
      return WPP_RECORDER_AND_TRACE_SF_sSD(*(_QWORD *)(v18 + 16), v19, v21, *(_QWORD *)(v18 + 40));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c7f0  mov     rax, rsp
0x18001c7f3  mov     [rax+8], rbx
0x18001c7f7  mov     [rax+10h], rsi
0x18001c7fb  push    rdi
0x18001c7fc  push    r14
0x18001c7fe  push    r15
0x18001c800  sub     rsp, 60h
0x18001c804  mov     edi, edx
0x18001c806  mov     dword ptr [rax+18h], 0
0x18001c80d  mov     rsi, rcx
0x18001c810  lea     rdx, [rax+18h]
0x18001c814  mov     ecx, edi
0x18001c816  call    BthGetPolicyValue
0x18001c81b  lea     r14, WPP_GLOBAL_Control
0x18001c822  mov     r9d, eax
0x18001c825  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c82c  mov     ebx, 1
0x18001c831  test    eax, eax
0x18001c833  jns     loc_18001C8DD
0x18001c839  mov     edx, edi
0x18001c83b  sub     edx, ebx
0x18001c83d  jz      short loc_18001C879
0x18001c83f  sub     edx, ebx
0x18001c841  jz      short loc_18001C875
0x18001c843  sub     edx, 2
0x18001c846  jz      short loc_18001C875
0x18001c848  sub     edx, 4
0x18001c84b  jz      short loc_18001C875
0x18001c84d  sub     edx, 8
0x18001c850  jz      short loc_18001C875
0x18001c852  sub     edx, 10h
0x18001c855  jz      short loc_18001C871
0x18001c857  sub     edx, 20h ; ' '
0x18001c85a  jz      short loc_18001C871
0x18001c85c  sub     edx, 3C0h
0x18001c862  jz      short loc_18001C875
0x18001c864  cmp     edx, 400h
0x18001c86a  jz      short loc_18001C871
0x18001c86c  or      eax, 0FFFFFFFFh
0x18001c86f  jmp     short loc_18001C87E
0x18001c871  xor     eax, eax
0x18001c873  jmp     short loc_18001C87E
0x18001c875  mov     eax, ebx
0x18001c877  jmp     short loc_18001C87E
0x18001c879  mov     eax, 2
0x18001c87e  mov     [rsp+78h+Data], eax
0x18001c885  mov     r10, cs:WPP_GLOBAL_Control
0x18001c88c  cmp     r10, r14
0x18001c88f  jz      short loc_18001C89D
0x18001c891  cmp     byte ptr [r10+19h], 3
0x18001c896  jb      short loc_18001C89D
0x18001c898  mov     r11b, bl
0x18001c89b  jmp     short loc_18001C8A0
0x18001c89d  xor     r11b, r11b
0x18001c8a0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c8a7  setnz   r8b
0x18001c8ab  test    r11b, r11b
0x18001c8ae  jnz     short loc_18001C8B5
0x18001c8b0  test    r8b, r8b
0x18001c8b3  jz      short loc_18001C8DD
0x18001c8b5  mov     ecx, edi
0x18001c8b7  call    BthGetPolicyName
0x18001c8bc  mov     rcx, [r10+10h]
0x18001c8c0  mov     dl, r11b
0x18001c8c3  mov     [rsp+78h+var_28], r9d
0x18001c8c8  mov     r9, [r10+28h]
0x18001c8cc  mov     [rsp+78h+var_30], rax
0x18001c8d1  mov     [rsp+78h+var_48], 0Ah
0x18001c8d8  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001c8dd  mov     ecx, edi
0x18001c8df  call    BthGetPolicyKeyValueName
0x18001c8e4  xor     edx, edx; lpSubKey
0x18001c8e6  mov     [rsp+78h+cbData], 4; cbData
0x18001c8ee  mov     r8, rax; lpValueName
0x18001c8f1  mov     rcx, rsi; hKey
0x18001c8f4  lea     rax, [rsp+78h+Data]
0x18001c8fc  mov     [rsp+78h+lpData], rax; lpData
0x18001c901  lea     r9d, [rdx+4]; dwType
0x18001c905  call    cs:__imp_RegSetKeyValueW
0x18001c90b  mov     r8d, eax
0x18001c90e  test    eax, eax
0x18001c910  jle     short loc_18001C91D
0x18001c912  movzx   r8d, ax
0x18001c916  or      r8d, 80070000h
0x18001c91d  test    r8d, r8d
0x18001c920  jns     short loc_18001C975
0x18001c922  mov     r10, cs:WPP_GLOBAL_Control
0x18001c929  cmp     r10, r14
0x18001c92c  jz      short loc_18001C935
0x18001c92e  cmp     byte ptr [r10+19h], 2
0x18001c933  jnb     short loc_18001C937
0x18001c935  xor     bl, bl
0x18001c937  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c93e  setnz   r11b
0x18001c942  test    bl, bl
0x18001c944  jnz     short loc_18001C94B
0x18001c946  test    r11b, r11b
0x18001c949  jz      short loc_18001C975
0x18001c94b  mov     ecx, edi
0x18001c94d  call    BthGetPolicyName
0x18001c952  mov     rcx, [r10+10h]
0x18001c956  mov     dl, bl
0x18001c958  mov     r9, [r10+28h]
0x18001c95c  mov     [rsp+78h+var_28], r8d
0x18001c961  mov     r8b, r11b
0x18001c964  mov     [rsp+78h+var_30], rax
0x18001c969  mov     [rsp+78h+var_48], 0Bh
0x18001c970  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001c975  lea     r11, [rsp+78h+var_18]
0x18001c97a  mov     rbx, [r11+20h]
0x18001c97e  mov     rsi, [r11+28h]
0x18001c982  mov     rsp, r11
0x18001c985  pop     r15
0x18001c987  pop     r14
0x18001c989  pop     rdi
0x18001c98a  retn
```

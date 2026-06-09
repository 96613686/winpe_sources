# ProcessCreateNotification

- ea: `0x14000aca0`
- end: `0x14000ade0`
- name: `ProcessCreateNotification`
- size: `320`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000adf0`

## callees

- `0x140001090`
- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x1400016ac`
- `0x14000a3c4`
- `0x14000aca0`
- `0x14000b76c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ad67`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ad67`

## string_xrefs

- `0x14000acb8`: `UevFilter.ProcessCreateNotification: Entry\n`
- `0x14000ad17`: `UevFilter.ProcessCreateNotification: Process name = %wZ\n`
- `0x14000adb8`: `UevFilter.ProcessCreateNotification: Failed to obtain the process name, status = 0x%X\n`
- `0x14000adc4`: `UevFilter.ProcessCreateDestroyNotification: Exit\n`

## pseudocode

```c
__int64 __fastcall ProcessCreateNotification(int a1, __int64 a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int v7; // ebx
  __int64 v8; // rdx
  UNICODE_STRING String1; // [rsp+30h] [rbp-10h] BYREF
  ULONG v11; // [rsp+68h] [rbp+28h] BYREF
  int v12; // [rsp+70h] [rbp+30h] BYREF
  int SenderBuffer; // [rsp+78h] [rbp+38h] BYREF
  int v14; // [rsp+7Ch] [rbp+3Ch]

  String1 = 0;
  DbgTrace(2, "UevFilter.ProcessCreateNotification: Entry\n");
  if ( a2 )
  {
    if ( (int)GetFileNameFromPath(*(_QWORD *)(a2 + 48), &String1) < 0 )
    {
      DbgTraceFrmtErr("UevFilter.ProcessCreateNotification: Failed to obtain the process name, status = 0x%X\n");
    }
    else
    {
      if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 0x10) != 0 )
        McTemplateK0hzr0q_EtwWriteTransfer(v5, v4, v6, String1.Length >> 1, (__int64)String1.Buffer, a1);
      DbgTraceFrmt(2, "UevFilter.ProcessCreateNotification: Process name = %wZ\n", &String1);
      if ( (unsigned __int8)IsProcessListedUnderRegistryKey(&String1, &stru_140007058)
        || (unsigned __int8)IsProcessListedUnderRegistryKey(&String1, &stru_140007048) )
      {
        DbgTrace(2, "UevFilter.IsRestrictedProcess: Entry\n");
        v7 = RtlEqualUnicodeString(&String1, &String2, 1u);
        DbgTraceFrmt(2, "UevFilter.IsRestrictedProcess: Exit, retValue = 0x%X\n", v7);
        if ( !(_BYTE)v7 )
        {
          v12 = 0;
          v11 = 4;
          SenderBuffer = 1;
          v14 = a1;
          ComPortSendMsg(&SenderBuffer, v8, &v12, &v11);
        }
      }
    }
  }
  return DbgTrace(2, "UevFilter.ProcessCreateDestroyNotification: Exit\n");
}

```

## disassembly

```asm
0x14000aca0  mov     [rsp-18h+arg_0], rbx
0x14000aca5  push    rbp
0x14000aca6  push    rsi
0x14000aca7  push    rdi
0x14000aca8  mov     rbp, rsp
0x14000acab  sub     rsp, 40h
0x14000acaf  mov     rbx, rdx
0x14000acb2  mov     rdi, rcx
0x14000acb5  xorps   xmm0, xmm0
0x14000acb8  lea     rdx, aUevfilterProce; "UevFilter.ProcessCreateNotification: En"...
0x14000acbf  mov     esi, 2
0x14000acc4  mov     ecx, esi
0x14000acc6  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14000acca  call    DbgTrace
0x14000accf  test    rbx, rbx
0x14000acd2  jz      loc_14000ADC4
0x14000acd8  mov     rcx, [rbx+30h]
0x14000acdc  lea     rdx, [rbp+String1]
0x14000ace0  call    GetFileNameFromPath
0x14000ace5  test    eax, eax
0x14000ace7  js      loc_14000ADB6
0x14000aced  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 10h
0x14000acf4  jz      short loc_14000AD11
0x14000acf6  movzx   r9d, [rbp+String1.Length]
0x14000acfb  mov     rax, [rbp+String1.Buffer]
0x14000acff  shr     r9w, 1
0x14000ad03  mov     [rsp+40h+var_18], edi
0x14000ad07  mov     [rsp+40h+var_20], rax
0x14000ad0c  call    McTemplateK0hzr0q_EtwWriteTransfer
0x14000ad11  lea     r8, [rbp+String1]
0x14000ad15  mov     ecx, esi
0x14000ad17  lea     rdx, aUevfilterProce_2; "UevFilter.ProcessCreateNotification: Pr"...
0x14000ad1e  call    DbgTraceFrmt
0x14000ad23  lea     rdx, stru_140007058; SourceString
0x14000ad2a  lea     rcx, [rbp+String1]; Source
0x14000ad2e  call    IsProcessListedUnderRegistryKey
0x14000ad33  test    al, al
0x14000ad35  jnz     short loc_14000AD4B
0x14000ad37  lea     rdx, stru_140007048; SourceString
0x14000ad3e  lea     rcx, [rbp+String1]; Source
0x14000ad42  call    IsProcessListedUnderRegistryKey
0x14000ad47  test    al, al
0x14000ad49  jz      short loc_14000ADC4
0x14000ad4b  lea     rdx, aUevfilterIsres; "UevFilter.IsRestrictedProcess: Entry\n"
0x14000ad52  mov     ecx, esi
0x14000ad54  call    DbgTrace
0x14000ad59  mov     r8b, 1; CaseInSensitive
0x14000ad5c  lea     rdx, String2; String2
0x14000ad63  lea     rcx, [rbp+String1]; String1
0x14000ad67  call    cs:__imp_RtlEqualUnicodeString
0x14000ad6e  nop     dword ptr [rax+rax+00h]
0x14000ad73  movzx   ebx, al
0x14000ad76  lea     rdx, aUevfilterIsres_0; "UevFilter.IsRestrictedProcess: Exit, re"...
0x14000ad7d  mov     r8d, ebx
0x14000ad80  mov     ecx, esi
0x14000ad82  call    DbgTraceFrmt
0x14000ad87  test    bl, bl
0x14000ad89  jnz     short loc_14000ADC4
0x14000ad8b  lea     r9, [rbp+arg_8]
0x14000ad8f  mov     [rbp+arg_10], 0
0x14000ad96  lea     r8, [rbp+arg_10]
0x14000ad9a  mov     [rbp+arg_8], 4
0x14000ada1  lea     rcx, [rbp+SenderBuffer]; SenderBuffer
0x14000ada5  mov     [rbp+SenderBuffer], 1
0x14000adac  mov     [rbp+arg_1C], edi
0x14000adaf  call    ComPortSendMsg
0x14000adb4  jmp     short loc_14000ADC4
0x14000adb6  mov     edx, eax
0x14000adb8  lea     rcx, aUevfilterProce_1; "UevFilter.ProcessCreateNotification: Fa"...
0x14000adbf  call    DbgTraceFrmtErr
0x14000adc4  lea     rdx, aUevfilterProce_10; "UevFilter.ProcessCreateDestroyNotificat"...
0x14000adcb  mov     ecx, esi
0x14000adcd  call    DbgTrace
0x14000add2  mov     rbx, [rsp+40h+arg_0]
0x14000add7  add     rsp, 40h
0x14000addb  pop     rdi
0x14000addc  pop     rsi
0x14000addd  pop     rbp
0x14000adde  retn
```

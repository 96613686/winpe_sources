# GetTemplate

- ea: `0x180115df0`
- end: `0x180115e30`
- name: `GetTemplate`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180115cc0`

## callees

- `0x180115df0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180115df8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180115e0e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180115df8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180115e0e`

## string_xrefs

- `0x180115e1b`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataPolicyManager">\n    <Key>\n      <Category>ConfigSource</Category>\n      <Path>HKLM\OSData\Software\Microsoft\PolicyManager\providers\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Key>\n        <Category>PolicyScope</Category>\n        <Path>default\*</Path>\n        <Representation>PolicyScope</Representation>\n        <Key>\n          <Category>Area</Category>\n          <Path>*</Path>\n   `
- `0x180115e14`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="PolicyManager">\n    <Key>\n      <Category>ConfigSource</Category>\n      <Path>HKLM\Software\Microsoft\PolicyManager\providers\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Key>\n        <Category>PolicyScope</Category>\n        <Path>default\*</Path>\n        <Representation>PolicyScope</Representation>\n        <Key>\n          <Category>Area</Category>\n          <Path>*</Path>\n          <Repre`
- `0x180115e05`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataPolicyManagerMeta">\n    <Key>\n      <Category>AreaMetadata</Category>\n      <Path>HKLM\OSData\Software\Microsoft\PolicyManager\default\*</Path>\n      <Representation>PolicyAreaName</Representation>\n      <Key>\n        <Category>PolicyMetadata</Category>\n        <Path>*</Path>\n        <Representation>PolicyName</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueR`
- `0x180115dfe`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="PolicyManagerMeta">\n    <Key>\n      <Category>AreaMetadata</Category>\n      <Path>HKLM\Software\Microsoft\PolicyManager\default\*</Path>\n      <Representation>PolicyAreaName</Representation>\n      <Key>\n        <Category>PolicyMetadata</Category>\n        <Path>*</Path>\n        <Representation>PolicyName</Representation>\n        <Value>\n          <Name>*</Name>\n          <ValueRepresentation>*</ValueRepresentation`

## pseudocode

```c
const wchar_t *__fastcall GetTemplate(char a1)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v2; // rdx
  const wchar_t *v3; // rcx

  if ( a1 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v2 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"PolicyManagerMeta\">\n"
          "    <Key>\n"
          "      <Category>AreaMetadata</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\default\\*</Path>\n"
          "      <Representation>PolicyAreaName</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyMetadata</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    v3 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataPolicyManagerMeta\">\n"
          "    <Key>\n"
          "      <Category>AreaMetadata</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\default\\*</Path>\n"
          "      <Representation>PolicyAreaName</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyMetadata</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v2 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"PolicyManager\">\n"
          "    <Key>\n"
          "      <Category>ConfigSource</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\providers\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyScope</Category>\n"
          "        <Path>default\\*</Path>\n"
          "        <Representation>PolicyScope</Representation>\n"
          "        <Key>\n"
          "          <Category>Area</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyAreaName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>CurrentPolicies</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\current\\*</Path>\n"
          "      <Representation>PolicyScope</Representation>\n"
          "      <Key>\n"
          "        <Category>CurrentPolicyValues</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyAreaName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>EASPolicy</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\EASCache\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyCategory</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Importance</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXPolicyMetaData</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\ADMXDefault\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>AreaName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ADMXIngestedAreaName</Representation>\n"
          "        <Key>\n"
          "          <Category>PolicyMetadata</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXInstallData</Category>\n"
          "      <Path>HKLM\\Software\\Microsoft\\PolicyManager\\AdmxInstalled\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>ADMXIngestedAppName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>AppName</Representation>\n"
          "        <Key>\n"
          "            <Category>ADMXIngestedSettingType</Category>\n"
          "            <Path>*</Path>\n"
          "            <Representation>SettingType</Representation>\n"
          "            <Key>\n"
          "              <Category>ADMXIngestedFileID</Category>\n"
          "              <Path>*</Path>\n"
          "              <Representation>FileUID</Representation>\n"
          "              <Value>\n"
          "                <Name>*</Name>\n"
          "                <ValueRepresentation>*</ValueRepresentation>\n"
          "              </Value>\n"
          "            </Key>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
    v3 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?>\n"
          "<DiagData>\n"
          "  <DataSource name=\"OSDataPolicyManager\">\n"
          "    <Key>\n"
          "      <Category>ConfigSource</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\providers\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyScope</Category>\n"
          "        <Path>default\\*</Path>\n"
          "        <Representation>PolicyScope</Representation>\n"
          "        <Key>\n"
          "          <Category>Area</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyAreaName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>CurrentPolicies</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\current\\*</Path>\n"
          "      <Representation>PolicyScope</Representation>\n"
          "      <Key>\n"
          "        <Category>CurrentPolicyValues</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>PolicyAreaName</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>EASPolicy</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\EASCache\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>PolicyCategory</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>Importance</Representation>\n"
          "        <Value>\n"
          "          <Name>*</Name>\n"
          "          <ValueRepresentation>*</ValueRepresentation>\n"
          "        </Value>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXPolicyMetaData</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\ADMXDefault\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>AreaName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>ADMXIngestedAreaName</Representation>\n"
          "        <Key>\n"
          "          <Category>PolicyMetadata</Category>\n"
          "          <Path>*</Path>\n"
          "          <Representation>PolicyName</Representation>\n"
          "          <Value>\n"
          "            <Name>*</Name>\n"
          "            <ValueRepresentation>*</ValueRepresentation>\n"
          "          </Value>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "    <Key>\n"
          "      <Category>IngestedADMXInstallData</Category>\n"
          "      <Path>HKLM\\OSData\\Software\\Microsoft\\PolicyManager\\AdmxInstalled\\*</Path>\n"
          "      <Representation>EnrollmentId</Representation>\n"
          "      <Key>\n"
          "        <Category>ADMXIngestedAppName</Category>\n"
          "        <Path>*</Path>\n"
          "        <Representation>AppName</Representation>\n"
          "        <Key>\n"
          "            <Category>ADMXIngestedSettingType</Category>\n"
          "            <Path>*</Path>\n"
          "            <Representation>SettingType</Representation>\n"
          "            <Key>\n"
          "              <Category>ADMXIngestedFileID</Category>\n"
          "              <Path>*</Path>\n"
          "              <Representation>FileUID</Representation>\n"
          "              <Value>\n"
          "                <Name>*</Name>\n"
          "                <ValueRepresentation>*</ValueRepresentation>\n"
          "              </Value>\n"
          "            </Key>\n"
          "        </Key>\n"
          "      </Key>\n"
          "    </Key>\n"
          "  </DataSource>\n"
          "</DiagData>";
  }
  if ( !IsStateSeparationEnabled )
    return v2;
  return v3;
}

```

## disassembly

```asm
0x180115df0  sub     rsp, 28h
0x180115df4  test    cl, cl
0x180115df6  jz      short loc_180115E0E
0x180115df8  call    cs:__imp_RtlIsStateSeparationEnabled
0x180115dfe  lea     rdx, aXmlVersion10En_1; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180115e05  lea     rcx, aXmlVersion10En_18; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180115e0c  jmp     short loc_180115E22
0x180115e0e  call    cs:__imp_RtlIsStateSeparationEnabled
0x180115e14  lea     rdx, aXmlVersion10En_15; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180115e1b  lea     rcx, aXmlVersion10En_10; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180115e22  test    al, al
0x180115e24  cmovz   rcx, rdx
0x180115e28  mov     rax, rcx
0x180115e2b  add     rsp, 28h
0x180115e2f  retn
```
